# General Purpose GPU
## Principal Arguments
[[Amdahl's law]]
[[Gustafson's law]]
[[Parallelism]]
[[GPU Hardware]]
[[Stream processing]]
[[GPGPU Program Flow]]
## Secondary Arguments
[[Concurrency]]
[[Bandwidth]]
[[latency]]
[[GPGPU Device Communication]]
## Misc knowledge
### Demand & Supply
#### Demand
- ***monitoring***
  huge amounts of data to analyze in real time;

- ***modelling***
  study, validation and application of models (economics, geophysics, mechanics, …);

- ***simulations***
  forecasting (e.g. meteorology), scenarios for a variety of phenomena (natural disaster, infrastructure failure, …)
#### Supply
- ***cluster***
  traditional solution; n computer (nodes) connected with high-speed networks;

- ***GPU***
  recent ‘accidental’ solution: originally developed for videogames, people find they are also excellent for general-purpose parallel computing

- ***accelerators***
  takes off from the success of GPUs, rely on the same principles, but lack graphics specialization (e.g. Xeon Phi).




## Wide cores
A GPU multiprocessor (MP) has multiple *processing elements* (PE), but they do not act independently from each other (similar to SIMD lanes, but with hardware-managed scheduling). Hardware and semantic details depend on architecture.

Limited flow control: optimized for predication, lane masking, no irreducible control flow (spaghetti code), no or limited recursion.

Note

GPUs run *groups of work-item* in lock-step. The group (*warp* in NVIDIA-speak, *wavefront* in AMD-speak) has a fixed size which is the SIMT width of the hardware. Even if you launch a single work-item, *a full warp/wavefront* will run!
### NVIDIA: *warp* size 32
Tesla (Compute Capability 1)

- 8 PE/MP, 4 cycles per warp, 1 scheduler/MP;

Fermi (Compute Capability 2)

- 2×16 PE/MP, 2 cycles per warp, 2 schedulers/MP
- 3×16 PE/MP, 2 cycles per warp, 2 schedulers/MP,\
  dual-issue;

Kepler (Compute Capability 3)

- 6×32 PE/MP, 1 cycle per warp, 4 schedulers/MP,\
  dual-issue;

Maxwell (Compute Capability 5)

- 4×32 PE/MP, 1 cycle per warp, 4 schedulers/MP,\
  dual-isse only for compute + load/store.
### AMD: *wavefront* size 64
Very different architecture, an *Ultra-Threaded Dispatch Processor* (UTDP) schedules wavefronts across all compute units.

TeraScale 1, 2 **(VLIW5)**

16×5 PE/MP, 4 cycles per wavefront

TeraScale 3 **(VLIW4)**

16×4 PE/MP, 4 cycles per wavefront

Graphic Core Next **(scalar)**

4×16 PE/MP, 4 cycles per wavefront, 4 wavefronts at a time
## High-bandwidth, high-latency
GPU memory controllers: high bandwidth, high latency.

High latency

a transaction might take 100s of cycles to complete.

High bandwidth

a single transaction can serve a whole subgroup (warp/wavefront) under optimal conditions.

Optimal conditions

a “pixel”- or “vertex”-worth of data per work-item, for *contiguous* groups of “pixels”. How does this translate for compute?
### Optimal data types
Preferred data types: 32-bit, 64-bit or 128-bit data types, i.e. `int`, `float`, or vector type such as

```
struct float2 {
    float x; float y;
};
```

and

```
struct float4 {
    float x; float y; float z; float w;
};
```

Try to keep it *aligned* and *contiguous*.
### Optimal data layout
Supported data types have alingment constraints, *typically* the type size.

Data alignment

- a `float` (size: 4 bytes) is read with a single transaction if its first byte is at an address which is a multiple of 4 (“4-byte boundary”)
- a `float2` is 2×`float`, but single transaction only if at 8-byte boundary.
- a `float4` is 4×`float`, but single transaction only if at 16-byte boundary.
- what about a `float3`? (hint: ‘it depends’)
### Optimal data layout (bis)
Subgroup alignment

subgroup (warp/wavefront) is served optimally for contiguous data aligned on multiple-of-data-alignment boundaries (i.e. first datum must be on a boundary which is a multiple of the number of values that the hardware can provide in a single transaction).
### Transaction model examples
Consider for example a class of old GPU without global memory cache,

NVIDIA GPUs with Compute Capability 1.x

half-warp granularity for transactions (16 work-items). A single transaction loads:

- 16 4-byte words in a 64-byte segment (e.g. `float`)
- 16 8-byte words in a 128-byte segment (e.g.`float2`)

Two transactions load;

- 16 16-byte words in two *consecutive* 128-byte segment (e.g.`float4`)

Other architectures *may* have (more or less effective) global memory cache, which may help hide inefficient layout choices. But *beware* of relying on this too much.
### Data layout hints
Preserve alignment

- e.g., prefer `float4` to `float3` even if fourth component is not needed;

Preserve contiguity

prefer structure of arrays (SoA) over arrays of structures (AoS);

Do not rely on caching

sometimes, bypassing the cache and using a good layout is better than exploiting the cache!

(*Note*: *do* use the cache(s) as much as possible, but lay out your data optimally regardless.)
## Memory layout examples
Set up a *particle system*.

Each particle has the properties:

- *position* in space (3 coordinates);
- spatial *velocity* (3 components).

How do you proceed?
### The worst possible way
```
typedef struct particle {
    float3 pos;
    float3 vel;
} particle_t;

kernel void
iteration(global particle_t *particles)
{
    int workitem = get_global_id(0);
    float3 pos = particles[workitem].pos;
    float3 vel = particles[workitem].vel;
    /* do stuff */
}
```

Results in inefficient, *repeated* loads.

Worst-case: 4 transactions per work-item.
### Avoid repeated loads
```
typedef struct particle {
    float3 pos;
    float3 vel;
} particle_t;

kernel void
iteration(global particle_t *particles)
{
    int workitem = get_global_id(0);
    particle_t pdata = particles[workitem];
    /* do stuff */
}
```

May improve over the previous one, depending on presence/efficiency of GPU caches. The whole `struct` can be loaded as three `float2` loads, if the compiler is smart enough. (Note that it cannot be loaded as a `float4`+`float2` due to alignment constraints.)

Worst-case: 3 transactions per work-item.
### Align to float4
```
typedef struct particle {
    float4 pos; /* ignore 4th component */
    float4 vel; /* ignore 4th component */
} particle_t;

kernel void
iteration(global particle_t *particles)
{
    int workitem = get_global_id(0);
    particle_t pdata = particles[workitem];
    /* do stuff */
}
```

As previous, but compiler knows that it can load each element of the `struct` as a `float4`. Better if you only need to load `pos` or `vel`. Cache usage might be worse.

Worst-case: 2 transactions per work-item.
### The efficient way
```
kernel void
iteration(
    global float4 * restrict posArray,
    global float4 * restrict velArray)
{
    int workitem = get_global_id(0);
    float4 pos = posArray[workitem]; /* ignore 4th component */
    float4 vel = velArray[workitem]; /* ignore 4th component */
    /* do stuff */
}
```

All work-items in a subgroup load `pos` in a single transaction and `vel` in another (single) transaction: two transactions load all the data *for the whole warp/wavefront*.

Hint

you can store extra info in the 4th component, e.g. *mass* and *density*, if you need additional properties.
### Why is AoS inefficient?
![Particle system loading patterns](https://www.dmi.unict.it/bilotta/gpgpu/newnotes/particle-layout.svg)

Particle system loading patterns[(zoom)](https://www.dmi.unict.it/bilotta/gpgpu/newnotes/particle-layout.svg)
## Asynchronicity
command queue (CUDA stream)

implicit or explicit list of commands that the host issues on a device; each device is controlled by one (or more) command queues.

Commands are executed *asynchronously*: the host queues the command, the device runs them as soon as possible, the host can do other stuff in the mean time.

event

markers associated with commands to allow the host to synchronize with the devices.

The host can wait on events, query even status, or wait until the device has completed all commands.
# CUDA vs OpenCL
## Host API differences
CUDA

- full device control, including special features;
- raw pointers to device buffers;
- single-source, separate source possible (but not easy);
- context and queue management can be implicit or manual;
- large launch grids must be split manually;

OpenCL

- device abstraction, vendors can expose special features via extensions;
- abstract buffers, no raw device pointers (but see SVM in 2.0);
- separate source only;
- contexts and queues must be managed manually;
- automatic (platform) control of launch grid splitting.
## Device language differences
CUDA C++

- based on C++98 (preliminary support for C++11 in CUDA 7.5);
- no built-in standard library for vector math\
  (but see `nvVector.h` in the CUDA samples);
- no built-in syntax for vector selection and swizzling;
- device intrinsics exposed;
- global work-item ID must be assembled from hardware registers, no support for launch grid offsets;

OpenCL C

- based on C99 (C++14 proposed for OpenCL 2.1);
- extensive built-in standard library for vector math;
- extended syntax for vector selection and swizzling;
- vendors may expose device intrinsics via extensions;
- built-in methods to obtain any local and global ID, including support for launch grid offset.
# (end)

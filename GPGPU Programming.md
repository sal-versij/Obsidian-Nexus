# GPGPU Programming
```ad-def
title:Optimal data types
Preferred data types: 32-bit, 64-bit or 128-bit data types, i.e. `int`, `float`, or vector types.
```

```ad-def
title:Optimal data layout
Supported data types have alingment constraints, *typically* the type size.
```

```ad-attention
Try to keep it *aligned* and *contiguous*.
```

```ad-def
title:Data alignment

- a `float` (size: 4 bytes) is read with a single transaction if its first byte is at an address which is a multiple of 4 (“4-byte boundary”)
- a `float2` is 2×`float`, but single transaction only if at 8-byte boundary.
- a `float4` is 4×`float`, but single transaction only if at 16-byte boundary.
- what about a `float3`? (hint: ‘it depends’)

```
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

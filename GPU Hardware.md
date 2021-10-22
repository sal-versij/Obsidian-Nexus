# GPU Hardware
Parallel hardware can be classified as

- shared-memory
  units can read/write the same memory;

  > *example*: multiple processors on a single computer;

  Pro

  - simpler communication;
  - less latency;

  Con

  - concurrency problems;
  - limits to number of units, amount of memory.
- distributed-memory
  each unit has its own memory;

  > *example*: networked computers, nodes in a cluster;

  Pro

  - less concurrency problems
  - (theoretically) infinite scalability;

  Con

  - more complex communication;
  - higher latency.
- hybrid
  > *example*: multiprocessor nodes in a cluster
## Memory
A *device* has different kinds of memory:

```ad-def
title:global memory
collapse:true

main device memory; accessible by all work-items in a kernel; persistent across kernel launches
```

```ad-def
title:constant memory
collapse:true

read-only on device, written by host; persistent across kernel launches
```

```ad-def
title:images (CUDA texture)
collapse:true

global memory accessed via the GPU texture engines; offers multi-dimensional indexing, coordinate normalization, data normalization, spatial caching, (bi)linear interpolation
```

```ad-def
title:local memory (CUDA shared memory)
collapse:true

reserved work-group memory; accessible by all work-items in a work-group; volatile (scope: kernel launch)

```

```ad-def
title:private memory
collapse:true

private to each work-item; volatile; held in the registers of the compute unit, unless too much is being used, in which case it spills into global memory (register spills are what CUDA calls local memory) and performance suffers
```
## Wide cores
A GPU multiprocessor (MP) has multiple [[processing elements]] (PE), but they do not act independently from each other. Hardware and semantic details depend on architecture.

```ad-attention
collapse:true
title:Limited flow control
optimized for predication, lane masking, no irreducible control flow (spaghetti code), no or limited recursion.
```

```ad-note
title:Group size
GPUs run *groups of work-item* in lock-step. The group (*warp* in NVIDIA-speak, *wavefront* in AMD-speak) has a fixed size which is the SIMT width of the hardware. Even if you launch a single work-item, *a full warp/wavefront* will run!
```

```ad-note
title:High-bandwidth, high-latency
GPU memory controllers: high bandwidth, high latency.

High latency: a transaction might take 100s of cycles to complete.
High bandwidth: a single transaction can serve a whole subgroup (warp/wavefront) under optimal conditions.

Optimal conditions: a "pixel"- or "vertex"-worth of data per work-item, for *contiguous* groups of "pixels".

How does this translate for compute?
[[GPGPU Programming]]
```
## References
[[3D Hardware APIs]]

# Parallelism
```ad-def
title:task-based
each unit carries out a different job;
example: “assembly line” model;
```

```ad-def
title:data-based
all units do the same work, on (different) subsets of the data;
example: domain partitioning.
```
## Hardware-wise
```ad-def
title:SIMD
*single **instruction**, multiple data*: hardware instructions that operate on vectors (MMX, AltiVec, SSE, NEON, AVX, etc);
```

```ad-def
title:SPMD
*single **program**, multiple data*: a sequence of instructions will be executed by multiple units at the same time; may be supported in hardware or via software;
```

```ad-def
title:SIMT
*single **instruction**, multiple **threads***: the hardware automatically manages multiple threads that all execute the same instruction (hardware-based multi-processing).
```

## Software-wise


```ad-def
title:Multi-processing

single program starts multiple _thread_; **shared memory** model;  
_standard_ (on CPU): **OpenMP**.

```

```ad-def
title:Message-passing

multiple processes communicate by exchanging _messages_; **distributed memory** model;  
_standard_: **MPI** (_Message Passing Interface_).

```

```ad-def
title:Hybrid

multiple processes, each of which is multi-threaded.
```
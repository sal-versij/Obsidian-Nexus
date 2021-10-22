# Parallelism
```ad-def
multiple **units** work **at the same time** to complete a certain job.
```

Theoretical upper bound: $T_L(N) = \frac{T_0}{N}$ where $T_0$ serial runtime, $N$ number of units. Ideal speed-up: $S_L(N) = \frac{T_0}{T_L(Ν)} = Ν$. (No upper limit to the speed-up).

**Amdahl’s argument**: only a fraction $p$ of the program can be run in parallel. Upper bound for runtime:

$T_A(N) = p \frac{T_0}{N} + (1 - p) T_0$

Maximum speed-up:

$S_A(N) = \frac{T_0}{T_A(N)} = \frac{1}{p/N + (1 - p)}$

Upper limit to the speed-up: $\frac{1}{1-p}$.

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

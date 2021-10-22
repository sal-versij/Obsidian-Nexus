# Parallel programming
```ad-def
multiple **units** work **at the same time** to complete a certain job.
```

Theoretical upper bound: $T_L(N) = \frac{T_0}{N}$ where $T_0$ serial runtime, $N$ number of units. Ideal speed-up: $S_L(N) = \frac{T_0}{T_L(Ν)} = Ν$. (No upper limit to the speed-up).

**Amdahl’s argument**: only a fraction $p$ of the program can be run in parallel. Upper bound for runtime:

$T_A(N) = p \frac{T_0}{N} + (1 - p) T_0$

Maximum speed-up:

$S_A(N) = \frac{T_0}{T_A(N)} = \frac{1}{p/N + (1 - p)}$

Upper limit to the speed-up: $\frac{1}{1-p}$.


Parallel programming
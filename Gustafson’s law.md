### Gustafson's law
> Gustafson's law addresses the shortcomings of [[Amdahl's law]], which is based on the assumption of a fixed problem size, that is of an execution workload that does not change with respect to the improvement of the resources

$S_{\text{latency}}(s)=1-p+sp$

where

- $S_{\text{latency}}$ is the theoretical speedup in latency of the execution of the whole task;
- $s$ is the speedup in latency of the execution of the part of the task that benefits from the improvement of the resources of the system;
- $p$ is the percentage of the execution workload of the whole task concerning the part that benefits from the improvement of the resources of the system *before the improvement*.

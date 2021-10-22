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

!!!TODO!!!


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

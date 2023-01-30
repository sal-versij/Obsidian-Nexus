# OpenCL
```ad-def
_**Open** **C**omputing **L**anguage_: cross-platform, multi-vendor language and _API_ for parallel computing on massively parallel hardware (GPU, accelerators).

Replaces proprietary interfaces for GPGPU (NVIDIA **[[CUDA]]**, AMD **[[CAL]]**). Also supports [[CPU]], [[APU]], [[accelerators]].

Has even be extended to clusters (**[[SnuCL]]**, **[[VirtualCL]]**), maintaining the same architecture.
```

```ad-def
title:Platforms
A host may be connected to devices from different vendors. The **[[ICD System]]** allows runtime selection of the *platform* (vendor driver) to use. Each platform may expose only a subset of the devices in the system.
```
## References
[[OpenCL C]]

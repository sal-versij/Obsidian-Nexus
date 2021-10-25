# OpenCL C
The code for the device is **separate** from the code for the host (separate source file, or text *string* embedded in host source).

An [[OpenCL]] program must load and compile the device code at runtime.

```ad-note
title:Disadvantage
most [[OpenCL]] programs share large chunks of initialization code (boilerplate). One of the most boring parts of [[OpenCL]].
```

```ad-attention
title:Restrictions
- no function pointers
- no recursion
- no bitfields
- no variable-length array
- no standard includes
```
## API
| Operation                                                    | Methods                                                             |
| ------------------------------------------------------------ | ------------------------------------------------------------------- |
| number of work-items launched (global, work-group)           | `get_global_work_size`, `get_local_work_size`                       |
| identify each work-item and work-group                       | `get_global_id`, `get_local_id`, `get_group_id`                     |
| synchronize work-items in the same work-group                | `barrier`                                                           |
| select platform and device(s)                                | `clGetPlatformIDs`, `clGetDeviceIDs`                                |
| create context and command queue used to control the devices | `clCreateContext`, `clCreateCommandQueue`                           |
| allocate memory for the devices                              | `clCreateBuffer`                                                    |
| copy data between host and device                            | `clEnqueueReadBuffer`, `clEnqueueWriteBuffer`, `clEnqueueMapBuffer` |
| prepare kernel for execution                                 | `clCreateProgramWithSource`, `clBuildProgram`, `clCreateKernel`     |
| launch kernels                                               | `clSetKernelArg`, `clEnqueueNDRangeKernel`                          |
| measure kernel performance                                   | `clGetEventProfilingInfo`                                           |

---
## Additions for vector and parallel programming on GPU
- vector types (`int`n, `float`n etc for n = 2, 4, 8, 16);
- rich set of built-ins to operate on vector types;
- memory region qualifiers (`global`, `local`, `constant`);
- built-ins expose the concurrency of kernel instances:

```ad-note
title:Parallelism in OpenCL
OpenCL supports both data-based and task-based parallelism
- data
**SPMD**: each single kernel can be executed by multiple work-items; but also **SIMD**, native support for vector data types and instructions.

```

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
## primary built-in methods
Opera|Methods
-|-
number of work-items launched (global, work-group)|`get_global_work_size`, `get_local_work_size`
identify each work-item and work-group|`get_global_id`, `get_local_id`, `get_group_id`|
synchronize work-items in the same work-group|`barrier`
## Additions for vector and parallel programming on GPU
- vector types (`int`n, `float`n etc for n = 2, 4, 8, 16);
- rich set of built-ins to operate on vector types;
- memory region qualifiers (`global`, `local`, `constant`);
- built-ins expose the concurrency of kernel instances:

## OpenCL *API*
clGetPlatformIDs, clGetDeviceIDs

select platform and device(s);

clCreateContext, clCreateCommandQueue

create context and command queue used to control the devices;

clCreateBuffer

allocate memory for the devices;

clEnqueueReadBuffer, clEnqueueWriteBuffer, clEnqueueMapBuffer

copy data between host and device.
# OpenCL *API* (bis)
clCreateProgramWithSource, clBuildProgram, clCreateKernel

prepare kernel for execution;

clSetKernelArg, clEnqueueNDRangeKernel

launch kernels;

clGetEventProfilingInfo

measure kernel performance.
# Parallelism in OpenCL
OpenCL supports both

data-based

**SPMD**: each single kernel can be executed by multiple work-items; but also **SIMD**, native support for vector data types and instructions.

and

task-based

multiple kernels executed by one work-item each, possibly on different devices.

parallelism.
# Parallelism in OpenCL
OpenCL supports both

shared-memory

kernel running on one device;

and

distributed-memory

kernels running on different devices.

models.
# Properties
scalability

simple approach limited by individual device capabilities; different paradigm (GPU → multi-GPU), scalability limited by cost;

latency

low on single device; high between devices;

asynchronous *API*

device and host work independently (a form of **task-based** parallelism); the *host* manages synchronization (with and between devices).
# Pros and cons
Somewhat **low-level** interface, more complex to use, more boiler plate.

**New** approach, still in development.

Smaller software ecosystem, less mature tools. But things are improving (see e.g. Bolt, clMath, ArrayFire).

Great **flexibility**.

Excellent **investment**. Easy vectorized, parallel programming for both CPU and accelerators.

HPC is moving in this direction.

(The two most powerful supercomputer are based on accelerators (Intel Xeon Phi) and GPUs (NVIDIA Tesla K20x).)
# Let's get started
# First steps
Start from the simple stuff:

1. initialize a vector;
2. (initialize and) add two vectors;
3. ‘smoothing’ a vector;
4. a simple reduction (finding the sum of all the elements of a vector).

We'll start from C and move on to the parallel world of OpenCL.
# Vector init
### Standard C
```
void vecinit(int *vec, int numels) {
    for (i=0; i < numels; ++i)
        vec[i] = i;
}

int main(int argc, char *argv[]) {
    /* missing: define numels somehow */
    int *vec=calloc(numels, sizeof(int));
    vecinit(vec, numels);

    for (i=0; i < numels; ++i)
        printf("vec[%d] = %d\n", i, vec[i]);

    return 0;
}
```
# Vector init
### OpenCL: the kernel
Device code resides in its own file (e.g. `vecinit.ocl`):

```
/* The kernel: multiple instances will be run at once,
   one for each element of the array vec */
kernel void vecinit(global int *vec)
{
    /* index of the “current” instance */
    int i = get_global_id(0);
    vec[i] = i;
}
```
# Vector init
### OpenCL: host code (fragment)
```
cl_kernel vecinit;

cl_event run_vecinit(cl_mem vec, cl_int numels) {
    cl_event vecinit_evt; /* event for this run */

    clSetKernelArg(vecinit, 0, sizeof(vec), &vec);

    size_t gws[1] = { numels }; /* size of the launch grid */

    cl_int err = clEnqueueNDRangeKernel(que, vecinit,
        1, NULL, gws, NULL,
        0, NULL, &vecinit_evt);

    return vecinit_evt;
}
```
# Anatomy of an OpenCL command
```
    cl_int err = clEnqueueNDRangeKernel(
        que, /* command queue */
        vecinit, /* kernel */
        1, /* dimensions in the grid (1, 2 or 3) */
        NULL, /* offset, none in our case */
        gws, /* global work size */
        NULL, /* local work size, automatic in our case */
        0, NULL, /* number and list of events to wait for */
        &vecinit_evt); /* event associated with this command */
```
# Anatomy of an OpenCL command
Similarly, to download data:

```
    cl_int *host_vec = calloc(numels, sizeof(cl_int));

    cl_event wait_list[] = { vecinit_evt };

    cl_int err = clEnqueueReadBuffer(
        que, /* command queue */
        vec, /* buffer */
        CL_TRUE, /* blocking, or CL_FALSE, non-blocking */
        0, /* offset, in bytes, to start copying from */
        numels*sizeof(cl_int), /* bytes to copy */
        host_vec,
        1, wait_list, /* number and list of events to wait for */
        &downoad_evt); /* event associated with this command */
```
# The boilerplate
[Something to help](https://www.dmi.unict.it/bilotta/gpgpu/newnotes/ocl_boiler.h). Use the given file to reduce boilerplate in your main program to:

```
#include "ocl_boiler.h" /* also includes CL/cl.h */

int main(int argc, char *argv[]) {
    cl_platform_id p = select_platform();
    cl_device_id d = select_device(p);
    cl_context ctx = create_context(p, d);
    cl_command_queue que = create_queue(ctx, d);
    cl_program prog = create_program("kernels.ocl", ctx, d);

    /* Here starts the custom part: extract kernels,
     * allocate buffers, run kernels, get results */

    return 0;
}
```
# Getting the kernel
To launch a kernel, the host needs a *handle* to the kernel from the (runtime-compiled) device code:

```

cl_int err; /* will hold the API error status */
cl_kernel vecinit = clCreateKernel(
    prog, /* cl_program holding the compiled device code: */
    "vecinit", /* C string, name of the kernel */
    &err);
```
# OpenCL buffers
```
cl_int err; /* will hold the API error status */
cl_mem vec = clCreateBuffer(
    ctx, /* the context in which the buffer will be created */
    flags, /* creation flags */
    numels*sizeof(int), /* size of the buffer, in bytes */
    NULL, /* associated host buffer, host_ptr */
    &err);
```
# OpenCL buffers: notes
Buffers are *abstract* objects associated with the *context*, **not** with a specific *device*: they can *migrate* from one device to another depending on where the kernels that use them are run.

Buffers have *use flags* to hint how they will be used (for reading, for writing, or both).

Buffers can also have an associated *host array*, either for initialization or for mapping.
# OpenCL buffers: flags
`CL_MEM_READ_ONLY`, `CL_MEM_WRITE_ONLY`, `CL_MEM_READ_WRITE`

how the buffer will be used on the device;

`CL_MEM_USE_HOST_PTR`

the memory pointed to by `host_ptr` is used as device memory; implementations can cache it to device memory;

`CL_MEM_ALLOC_HOST_PTR`

the buffer should be allocated from host-accessible memory; this is mutually exclusive with `USE_HOST_PTR`;

`CL_MEM_COPY_HOST_PTR`

the buffer is initialized by copying the memory pointed at by `host_ptr`.
# Waiting for devices
The host can synchronize with devices using:

`clFlush(queue)`

wait until all commands in the queue have been *submitted* to the devices;

`clFinish(queue)`

wait until all commands in the queue have been *completed* on the devices;

`clWaitForEvents(num, wait_list)`

wait until all events in the `wait_list` have been *completed* on the devices.
# Measuring command performance
When profiling is enabled for a command queue, the events associated with each command provide the following information:

`CL_PROFILING_COMMAND_QUEUED`

when the command was put in the queue

`CL_PROFILING_COMMAND_SUBMIT`

when the command was submitted to the device

`CL_PROFILING_COMMAND_START`

when execution started

`CL_PROFILING_COMMAND_END`

when execution completed
# Measuring command performance (bis)
`ocl_boiler.h` provides `runtime_ms` to get a command runtime in milliseconds, `runtime_ns` to get a command runtime in nanoseconds.

The number of bytes read and written by a command, divided by the runtime in nanoseconds, gives the *effective bandwidth* in GB/sec.
# The next step: local data sharing and reductions
# Local data
Work-items *in the same work-group* can share data quickly using *local memory*.

Local memory is allocated *per work-group*, with contents not initialized at the beginning of the kernel. Contents do not persist after the kernel terminates.

The amount of local memory used *by each work-group* can be specified either statically (inside the kernel), or dynamically (by the host when launching the kernel). The latter is more common, as the amount typically relates to the work-group size and this may change from device to device.

Work-items must synchronize before reading data written by other work-items, using a memory fence: `barrier(CLK_LOCAL_MEM_FENCE)`.
# Local data: example
```
kernel void invert_lds( global int * restrict output,
            global const int * restrict input,
            local int * lds)
{
    const int gid = get_global_id(0); /* global index of the work-item */
    const int lid = get_local_id(0); /* local index of the work-item */

    lds[lid] = input[gid]; /* load data in local memory from global memory */

    /* wait for the other work-items in the work-group: */
    barrier(CLK_LOCAL_MEM_FENCE);

    /* here we can compute result using also the data
     * loaded by other work-items (omitted) */

    output[gid] = result; /* write out the final result */
}
```
# Parallel reduction
### The basics
Reduction

obtain one value from a set of values

Assumptions

the operation to obtain the value is commutative and associative (e.g. addition multiplication, minimum, maximum, etc).

Aims

1. have as many work-items working for as long as possible;
2. minimize access to global memory.
# Parallel reduction
### A possible idea
Naive approach:

- each work-item reads two elements and returns one element;
- each kernel launch halves the number of elements to reduce;
- launch the kernel multiple times (until we have a single value).

Issues:

- to reduce n elements we need log_2(n) kernel launches;
- total amount of reads \sum_k n/2^k, total amount of writes: \sum_k n/2^{k-1}, total amount of I/O operations: 3n, best effective bandwidth we can aim to: 33% of optimal.
# Parallel reduction
### The next step
- load data into local memory
- each work-groups does a naive reduction in local memory;
- each kernel launch produces one value *per work-group*;
- launch the kernel multiple times (until we have a single value).

Improvements:

- fewer kernel launches;
- less usage of slow global memory;

Can we improve it still?
# Parallel reduction
### The best thing
- do an initial reduction while reading from global memory;
- then reduce in local memory;
- still produce one value per work-group;

But:

- a single work-group can read multiple blocks of data;
  - in fact, a single work-group can reduce the entire data set (but it's not efficient);
- in practice, can be done with two launches:

  1. launch enough work-groups to saturate the hardware;
  2. a single work-group to do the final reduction.
# Parallel reduction
### Ideas behind the best thing
- optimal even without using large work-groups;
- still uses the whole hardware as much as possible;

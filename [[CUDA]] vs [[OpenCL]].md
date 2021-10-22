# [[CUDA]] vs [[OpenCL]]
## Host API differences
| CUDA                                                                                              | OpenCL                                                                                       |
| ------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| full device control                                                                               | device abstraction                                                                           |
| raw pointers to device buffers                                                                    | abstract buffers                                                                             |
| separate(difficult)/single-source                                                                 | separate source only                                                                         |
| implicit/manual context/queue management                                                          | manual contexts/queue management                                                             |
| manual grid split                                                                                 | automatic grid split                                                                         |
| based on C++98 (preliminary support for C++11 in CUDA 7.5)                                        | based on C99 (C++14 proposed for OpenCL 2.1)                                                 |
| no built-in standard library for vector math (but see `nvVector.h` in the CUDA samples)           | extensive built-in standard library for vector math                                          |
| no built-in syntax for vector selection and swizzling                                             | extended syntax for vector selection and swizzling                                           |
| device intrinsics exposed                                                                         | vendors may expose device intrinsics via extensions                                          |
| global work-item ID must be assembled from hardware registers, no support for launch grid offsets | built-in methods to obtain any local and global ID, including support for launch grid offset |

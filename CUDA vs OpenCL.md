# CUDA vs OpenCL
## Host API differences
| Property                 | [[CUDA]]                         | [[OpenCL]]      |
| ------------------------ | ---------------------------- | ----------- |
| device                   | full control                 | abstraction |
| buffer                   | raw pointers                 | abstract    |
| source                   | separate(difficult) / single | separate    |
| context/queue management | implicit/manual              | manual      |
| grid split               | manual                       | automatic   |

---
## Device language differences
| Property                          | [[CUDA]]                     | [[OpenCL]]                            |
| --------------------------------- | ------------------------ | --------------------------------- |
| language                          | C++                      | C (C++ proposed)                  |
| vector math                       | sample code              | extensive built-in std lib        |
| vector selection/swizzling syntax | no                       | extended syntax                   |
| device intrinsics                 | exposed                  | vendors may expose via extensions |
| global/local id                   | assembled from registers | built-in methods                  |
| launch grid offset                | not supported            | built-in methods                  |

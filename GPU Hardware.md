# GPU Hardware
Parallel hardware can be classified as

- shared-memory
  units can read/write the same memory;

  > *example*: multiple processors on a single computer;

  Pro

  - simpler communication;
  - less latency;

  Con

  - concurrency problems;
  - limits to number of units, amount of memory.
- distributed-memory
  each unit has its own memory;

  > *example*: networked computers, nodes in a cluster;

  Pro

  - less concurrency problems
  - (theoretically) infinite scalability;

  Con

  - more complex communication;
  - higher latency.
- hybrid
  > *example*: multiprocessor nodes in a cluster

# GPGPU Device Communication
Consider a modern, middle- or high-range setup.
*Host* memory bandwidth: around 50 GB/s.
*Device* memory bandwidth: 300–500 GB/s.
What about data transfers *between* the host and the device?

PCI-E 3.0 x16: less than 16GB/s *in the ideal case*:

- less than half the host RAM bandwidth;
- less than 1/20th of the device VRAM bandwidth.

Even the upcoming NVLink (64GB/s theoretical peak) has about an order of magnitude less than device VRAM bandwidth.

```ad-attention
title:Don’t do it
EVERY TIME YOU TRANSFER DATA BETWEEN HOST AND DEVICEDOMO KILLS A KITTEN

If you really must …
- minimize number of transfers;
- minimize amount of data;
- maximize parallelism (do something else *while* data is being copied).
```

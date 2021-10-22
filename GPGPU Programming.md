# GPGPU Programming
```ad-def
title:Optimal data types
Preferred data types: 32-bit, 64-bit or 128-bit data types, i.e. `int`, `float`, or vector types.
```

```ad-def
title:Optimal data layout
Supported data types have alingment constraints, *typically* the type size.
```

```ad-attention
Try to keep it *aligned* and *contiguous*.
```

```ad-def
title:Data alignment

- a `float` (size: 4 bytes) is read with a single transaction if its first byte is at an address which is a multiple of 4 (“4-byte boundary”)
- a `float2` is 2×`float`, but single transaction only if at 8-byte boundary.
- a `float4` is 4×`float`, but single transaction only if at 16-byte boundary.
- 
```

```ad-hint
collapse:true
title:Data layout hints
#### Preserve alignment
- e.g., prefer `float4` to `float3` even if fourth component is not needed;

#### Preserve contiguity
prefer structure of arrays (SoA) over arrays of structures (AoS);

#### Do not rely on caching
sometimes, bypassing the cache and using a good layout is better than exploiting the cache!
*Do* use the cache(s) as much as possible, but lay out your data optimally regardless.
```

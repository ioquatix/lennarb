# Performance

The **Lennarb** is very fast. The following benchmarks were performed on a MacBook Pro (Retina, 13-inch, Early 2013) with 2,7 GHz Intel Core i7 and 8 GB 1867 MHz DDR3. Based on [jeremyevans/r10k](https://github.com/jeremyevans/r10k) using the following [template build](static/r10k/build/lennarb.rb).

All tests are performed using the **Ruby 3.3.0**

## Benchmark numbers

This document contains the benchmarks comparing **Lennarb** with other routers based on Rack. Metrics evaluated include Requests per Second, Initial memory usage and Startup time.

### 1. Requests per Second (RPS)

| Position | Application | 10 RPS     | 100 RPS    | 1.000 RPS | 10.000 RPS |
| -------- | ----------- | ---------- | ---------- | --------- | ---------- |
| 1        | Lenna       | 126.252,36 | 108.086,55 | 87.111,91 | 68.460,64  |
| 2        | Roda        | 123.360,37 | 88.380,56  | 66.990,77 | 48.108,29  |
| 3        | Syro        | 114.105,38 | 80.909,39  | 61.415,86 | 46.639,81  |
| 4        | Hanami-API  | 68.089,18  | 52.851,88  | 40.801,78 | 27.996,00  |

This table ranks the routers by the number of requests they can process per second. Higher numbers indicate better performance.

### 2. Initial memory usage (in KB)

| Position | Application | 10 KB  | 100 KB | 1.000 KB | 10.000 KB |
| -------- | ----------- | ------ | ------ | -------- | --------- |
| 1        | Syro        | 12,160 | 12,544 | 16,460   | 49,692    |
| 2        | Lenna       | 14,464 | 14,720 | 18,232   | 56,812    |
| 3        | Roda        | 15,104 | 15,104 | 18,220   | 49,900    |
| 4        | Hanami-API  | 15,744 | 16,128 | 20,888   | 64,824    |

This table shows the initial memory usage in KB. Lower values indicate lower memory consumption.

### 3. Startup time (in seconds)

| Position | Application | 10 seg | 100 seg | 1.000 seg | 10.000 seg |
| -------- | ----------- | ------ | ------- | --------- | ---------- |
| 1        | Syro        | 0.274  | 0.347   | 0.455     | 0.997      |
| 2        | Lenna       | 0.289  | 0.312   | 0.393     | 0.914      |
| 3        | Roda        | 0.294  | 0.378   | 0.467     | 0.918      |
| 4        | Hanami-API  | 0.445  | 0.550   | 0.808     | 3.074      |

This table shows the startup time in seconds. Lower values indicate faster startup times.


## Graphs

### Requests per second (RPS)

![Benchmarks](../../static/rps.png)

### Initial memory usage

![Benchmarks](../../static/memory.png)

### Runtime startup

![Benchmarks](../../static/runtime_with_startup.png)


## Conclusion

These numbers are just a small reference, **Lennarb** is not a framework, it is a router. In my opinion, **Roda** is the best router for Ruby because it has many interesting features, such as a middleware manager, and very good development performance.

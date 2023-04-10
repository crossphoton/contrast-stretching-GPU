# contrast-stretching-GPU
Multiple Implementations of Contrast Stretching on GPU.

## Results
### Overall Speedup Comparison

| **Method**                            | **Kernel Time (us) (2<sup>22</sup> ints)** | **Bandwidth GB/s** | **Step Speedup** | **Cum. Speedup** |
|---------------------------------------|--------------------------------------------|--------------------|------------------|------------------|
| CPU                                   | 73611                                      | 0.2                | -                | -                |
| interleaved_addressing_0              | 2895                                       | 2.90               | 25.4             | 25.4             |
| interleaved_addressing_nondivergent_1 | 1776                                       | 9.44               | 1.63             | 41.44            |
| sequential_addressing_2               | 1590                                       | 10.52              | 1.16             | 46.29            |
| compare_in_load_3                     | 923                                        | 18.16              | 1.65             | 79.75            |
| warp_unrolling_4                      | 755                                        | 22.22              | 1.22             | 97.50            |


### Kernel Speedup

| **Method**                            | **Kernel Time (us) (2<sup>22</sup> ints)** | **Bandwidth GB/s** | **Step Speedup** | **Cum. Speedup** |
|---------------------------------------|--------------------------------------------|--------------------|------------------|------------------|
| CPU                                   | 23295.0                                    | 0.72               | -                | -                |
| interleaved_addressing_0              | 1208.6                                     | 13.88              | 19.27            | 19.27            |
| interleaved_addressing_nondivergent_1 | 703.71                                     | 23.84              | 1.72             | 33.103           |
| sequential_addressing_2               | 608.59                                     | 27.56              | 1.16             | 38.277           |
| compare_in_load_3                     | 334.22                                     | 50.20              | 1.82             | 69.69            |
| warp_unrolling_4                      | 251.67                                     | 66.66              | 1.33             | 92.56            |


## Reference
- https://developer.download.nvidia.com/assets/cuda/files/reduction.pdf

---
layout: docs
doc_title: NVIDIA HPC SDK
permalink: /documentation/software/nvhpc/
---

The NVIDIA HPC SDK provides CUDA-related tools such as `nvcc` to the end user. It includes all HPC libraries except for cuDNN which is loaded as a [separate module]({{ '/documentation/software/cudnn/' | relative_url }}).

Find out more [here](https://developer.nvidia.com/hpc-sdk)

To load the NVIDIA HPC SDK, run the following:
```
module load nvhpc
```

Due to NVHPC overwriting the local CC and CXX variables, by default it is not loaded. This means you will have to load the nvhpc module whenever you want to use any CUDA tools.

---
layout: docs
doc_title: CUDA Toolkit
permalink: /documentation/software/cudatoolkit/
---

This module does the exact same things as [NVHPC]({{ '/documentation/software/nvhpc/' | relative_url }}) and NVHPC is the preferred method of using CUDA. The only difference is that the CUDA Toolkit module also sets the `CUDA_HOME` directory.

The CUDA Toolkit module is only updated when `nvhpc` is updated.

To load CUDA Toolkit, run the following:

```
module load cudatoolkit
```

### Stock CUDA Toolkit

If you absolutely need a stock CUDA toolkit install, you can load the following module:

```
module load stockcuda/12.6.2
```

Since it is a stock CUDA install, some HPC libraries are missing. Due to this, it is highly recommended to use [NVHPC]({{ '/documentation/software/nvhpc/' | relative_url }}) instead. The stock CUDA toolkit module is also only sporadically updated.

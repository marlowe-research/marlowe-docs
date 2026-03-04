---
layout: docs
doc_title: SLURM on Marlowe
permalink: /documentation/slurm/
---

Marlowe uses SLURM, a job scheduling system, to run jobs. There are three main account types: Basic/Preempt, Medium/Batch, and Large/Hero.

The SLURM commands `srun`, `salloc`, and `sbatch` will take you far!

Marlowe accounts start with `marlowe-` followed by the project ID. So if your project ID was `m223813`, your account would be `marlowe-m223813`. To use the batch or hero partitions, you will need to add a suffix to your account, like `marlowe-m223813-pm01`. Read more about it in the [Accounts](#accounts) section below.

**SRUN**:

```
srun -N 1 -G 4 -A marlowe-[Project ID] -p preempt --pty bash
```

**SALLOC**:

```
salloc -N 1 -A marlowe-[Project ID] -p preempt
```

**SBATCH**:

```bash
#!/bin/sh

#SBATCH --job-name=test
#SBATCH -p preempt
#SBATCH --nodes=1
#SBATCH -A marlowe-[Project ID]
#SBATCH -G 1
#SBATCH --time=00:30:00
#SBATCH --error=~/foo.err

module load slurm
module load nvhpc
module load cudnn/cuda12/9.3.0.75

bash ~/test.sh
```

## Check GPU allocation usage

To see a medium project's usage, use its `pm` suffix. To see a large project's usage, use its `pl` suffix.

```bash
sreport cluster UserUtilizationByAccount -T gres/gpu Start=[start of billing cycle] End=now account=[your project account] -t hours
```

## Accounts

Each allocation is given a project ID. This project ID corresponds to a job account on Marlowe.

One of the requirements (for accounting purposes) is for each job to be credited to a job account. If you don't add a valid account, you will see the following error message when submitting jobs:

```
srun: error: ACCOUNT ERROR: Did you remember to set your account?
```

Medium and large projects are given a GPU hours allocation, tied to a suffix on the main project ID. The suffix is required when using the batch/medium and hero/large partitions. Users can keep track of their allocation using the sreport command above.

The suffix will be something like **pm**01 for a medium project, or **pl**01 for a large project. Check your Marlowe welcome email if you need your project's suffix.

<div class="docs-callout docs-callout-note">
<strong>Note</strong>
<p>You will be charged against your GPU hours allocation if you submit a job with a medium/large project suffix to the preempt partition.</p>
</div>


## Available Partitions

1. If you have a medium project allocation, you should submit to the **batch** partition
2. If you have a large project allocation, you should submit to the **hero** partition
3. For basic access, you can only submit to the **preempt** partition


## Partition Limits

**Hero**: 25 nodes, 24 hours

**Batch**: 16 nodes, two days

**Preempt**: 8 nodes, 12 hours

<div class="docs-callout docs-callout-note">
<strong>Note</strong>
<p>Any jobs in the <code>preempt</code> queue can be preempted within 15 minutes if a job in a higher priority partition (<code>batch</code> or <code>hero</code>) requests the node that the <code>preempt</code> job is running on.</p>
</div>

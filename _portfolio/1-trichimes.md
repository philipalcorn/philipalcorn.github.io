---
title: "TriChimes: GPU-Accelerated Machine-Learned Interatomic Potential"
excerpt: "NSF ACRES REU, Michigan State University (Summer 2026). Advisor: Dr. Dylan Anstine. A Triton GPU implementation of the ChIMES many-body potential that simulates 1 million atoms in just over 3 seconds per timestep."
collection: portfolio
order: 1
---

**NSF ACRES REU, Michigan State University, May–July 2026.** Advisor: Dr. Dylan Anstine

ChIMES is a many-body machine-learned interatomic potential whose reference implementation runs on the CPU. Molecular dynamics is highly parallel, so this project was a chance to study how the workload could be mapped efficiently onto a GPU.

- Built TriChimes, a GPU implementation of ChIMES in Triton and PyTorch, and validated it against the original CPU implementation
- Wrote fused GPU kernels for two- and three-body energy and force evaluation (neighbor lists, Chebyshev polynomial recurrences, atomic force accumulation), restructuring data layout and memory access for a nearly 1000× per-timestep speedup over the reference C++ code
- Eliminated redundant pair calculations and mapped pair interactions fully onto Triton blocks to reduce idle threads, reaching 1 million atoms in just over 3 s per timestep
- Reduced the number of model coefficients by identifying symmetric combinations of atom types
- Hand-wrote backward-pass kernels to remove autograd overhead in training
- Built a GPU-vs.-CPU benchmarking suite and pybind11 bindings to the ChIMES C++ library

The main lesson: performance gains come not only from faster arithmetic but from properly using the GPU's execution model.

Awarded **Second-Best Research Presentation** in the REU cohort.

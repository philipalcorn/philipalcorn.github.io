---
permalink: /
title: "About"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

I'm an electrical engineering student at [Tarleton State University](https://www.tarleton.edu/) (B.S. expected May 2027, 4.0 GPA). My research interests are in **computer architecture**: how hardware can be designed around the computational demands of the workloads it runs.

I came to architecture from the software side. While writing GPU kernels for cardiac and molecular dynamics simulations, I found that big performance gains often came from restructuring work to fit the hardware better, without changing the algorithm at all. That got me interested in the other direction: how the hardware itself should change to serve a workload.

Research interests
------
- Workload-driven architecture: using memory access patterns and available parallelism to guide the design of memory hierarchies, execution resources, and accelerators
- Domain-specific accelerators, particularly for sparse and irregular scientific workloads
- The trade-off between optimizing software for existing hardware and adding dedicated hardware for workload bottlenecks
- Modeling and simulation techniques for evaluating proposed hardware designs

Current and recent work
------
- **GPU molecular dynamics (NSF REU, Michigan State, 2026):** Built *TriChimes*, a Triton GPU implementation of the ChIMES machine-learned interatomic potential. It simulates 1 million atoms in just over 3 seconds per timestep, nearly 1000× faster per timestep than the reference C++ code.
- **Cardiac digital twin (Tarleton HPC Lab, 2025–2026):** Wrote a CUDA Monte Carlo extension for a near-real-time model of the human left atrium that automatically searches for fibrosis patterns likely to cause arrhythmias. I co-presented this work at NVIDIA GTC 2026, and it was published in *Heart Rhythm O2*.
- **FPGA CNN accelerator (senior capstone, in progress):** Designing a convolution accelerator that classifies live video on a Terasic DE1-SoC, with double-buffered layer control so the same hardware is reused across layers.

More on these projects is on the [Research](/portfolio/) page, and my full [CV](/cv/) is available as a PDF.

Outside of research, I'm a math tutor at Tarleton and was a Supplemental Instruction leader for University Physics. I chaired our IEEE student branch, where I started its robotics competition team, and I'm now the branch treasurer.

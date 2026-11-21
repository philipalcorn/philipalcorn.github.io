---
title: "Interactive Digital Twin of the Left Atrium"
excerpt: "Tarleton HPC Lab (2025–2026). Advisor: Dr. Bryant Wyatt. A CUDA Monte Carlo extension to an NIH-funded, near-real-time N-body model of the heart that automates the search for arrhythmia-causing fibrosis patterns. Presented at NVIDIA GTC 2026 and published in Heart Rhythm O2."
collection: portfolio
order: 2
---

**Tarleton HPC Lab, August 2025–May 2026.** Advisor: Dr. Bryant Wyatt

The lab builds an NIH-funded, CUDA-accelerated N-body model of the human left atrium that runs in near real time, used to simulate atrial arrhythmias and virtual catheter ablation. When I joined, running experiments was entirely manual.

- Proposed and implemented a CUDA Monte Carlo extension that automates the search for fibrosis patterns likely to induce arrhythmias under different electrodynamic conditions
- Built the pipeline that converts patient CT scans into simulation-ready geometry (C, CUDA, Python)
- Decoupled the rendering and compute pipelines to minimize device-to-host memory transfers, raising frame rate while preserving simulation accuracy

Co-presented at NVIDIA GTC 2026. Results were published in [*Heart Rhythm O2*](https://doi.org/10.1016/j.hroo.2026.05.020) and in two *Heart Rhythm 2026* abstracts (see [Publications](/publications/)).

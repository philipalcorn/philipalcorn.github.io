---
title: "FPGA CNN Accelerator"
excerpt: "Senior design project (Fall 2026–present). An input-stationary convolution accelerator in Verilog that classifies live video on a Terasic DE1-SoC, designed to minimize off-chip memory traffic."
collection: portfolio
order: 3
---

**Senior capstone, Fall 2026–present (in progress)**

An FPGA-based CNN accelerator, inspired by YOLOv8n, that classifies live video on a Terasic DE1-SoC. The focus is on bandwidth between the ARM processor and the FPGA and on making the most of limited on-chip resources.

- Input-stationary convolution accelerator in Verilog, with on-chip buffering to minimize off-chip memory traffic
- Double-buffered (ping-pong) layer control: each layer reads from one buffer and writes to the other, alternating between layers, so the convolution hardware is reused across layers and less on-chip memory is needed during inference
- Linux on the ARM HPS captures webcam frames into shared DDR3, and an Avalon-MM burst master streams them into the accelerator
- Exploring trade-offs between PE-array dataflow, line buffers, and fixed-point quantization against throughput and area

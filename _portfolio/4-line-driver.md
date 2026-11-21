---
title: "Gigabit Ethernet Line Driver"
excerpt: "Analog design project (Spring 2026). A two-stage Class AB transimpedance driver in 0.18 µm CMOS that produces a 1000BASE-T waveform with 0.16% THD while using 74% less static current than budgeted."
collection: portfolio
order: 4
---

**Analog IC design, Spring 2026.** 3.3 V, 0.18 µm CMOS

- Designed a two-stage Class AB transimpedance driver (folded cascode with a Monticelli bias cell) that converts a current-DAC output into a 1000BASE-T waveform on a 100 Ω load at 125 MHz
- Sized with a gm/Id methodology and verified across 8 LTspice testbenches
- Cut static ground current to 1.28 mA (74% under budget) while holding 0.16% THD, more than 80° loop-gain phase margin (two custom compensation networks), and 330 MHz bandwidth

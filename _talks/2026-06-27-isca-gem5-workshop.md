---
title: "[ISCA 2026] Bringing Arm Cortex-M to gem5: Enabling Embedded Robotics Research"
collection: talks
# type is a free-text label shown on the talk; existing values used on this site:
#   "Main Conference" | "Workshop" | "Tutorial"
type: "Workshop"
permalink: /talks/2026-isca-gem5-workshop
venue: "ISCA 2026"
date: 2026-06-27
# location is geocoded by the talkmap automation — use a real "City, Country" string.
location: "Raleigh, USA"
excerpt: "Introducing the Arm Cortex-M support in gem5 for robotic compute–software co-design."
---

## Overview

This talk introduces Arm Cortex-M (M-profile) support in **gem5**, enabling
hardware–software co-design research for embedded robotics. Modern robots such
as nano-drones run on Cortex-M MCUs (e.g. the STM32F4) under extreme size,
weight, and power (SWaP) constraints, yet still need to perform reactive
behaviors and increasingly complex tasks. Studying these systems requires a
cycle-level simulator that models the M-profile world accurately — something
gem5 previously lacked.

M-profile is not a restricted A/R core: it has its own ISA, a nested vectored
interrupt controller (NVIC) instead of the GIC, an optional MPU instead of an
MMU, an address vector table with Thread/Handler modes, and interrupt-latency
features (tail-chaining, late-arriving, and lazy floating-point stacking) that
have no A/R equivalent.

**Contributions of this work:**

- **Arm-M class decoder, registers, and instructions** — an M-profile decoder
  that intercepts M-specific encodings (MSR/MRS, CPS, SVC, BKPT, VFP,
  LDREX/STREX) and falls through to the shared A/R decoder generated from the
  same `.isa`.
- **M-profile fault model, System Control Space, thread handling, and NVIC** —
  hardware-resolved interrupt priority (PRIMASK/BASEPRI), automatic 8-word
  stack framing, vector fetch via VTOR, and `EXC_RETURN`-driven unstacking for
  low, predictable latency.
- **M-profile gem5 MMU and partial stacking optimization** — modeling
  tail-chaining, late-arriving preemption, and lazy FP save (skipping S0–S15
  stacking unless the handler uses FP).
- **M-profile Platform** — flexibly describe the memory and device layout of a
  board in Python.
- **gem5 stdlib Cortex-M board and STM32G474RE platform.**

**Evaluation:**

- *Functional correctness* — validated against real hardware using
  microbenchmarks, randomly generated instruction sequences, and selected
  Embench kernels involving heavy FP instructions, interrupts, and semihosting;
  thread handling validated by running FreeRTOS multithread workloads.
- *Performance error* — running the same binaries on both the real STM32G4
  board and gem5, the custom 3-stage CPU achieves 1.9% overall mean cycle error
  (vs. 34.5% for a tuned MinorCPU).
- *SoC-in-the-loop robotics* — a multi-robot cosimulation where Webots steps
  each robot and a bridge routes it to its own STM32G474RE gem5 instance.
  Example repository: [https://github.com/studyztp/webots-gem5-example](https://github.com/studyztp/webots-gem5-example)

## Presentation Slides

[Slides](/files/Arm-M-workshop.pdf)

## Related Publication

TBD

<!--
Save as: _talks/YYYY-MM-DD-slug.md
Rendered at: /talks/YYYY-venue-slug   (uses layout: talk automatically, per _config.yml)
AUTOMATION: pushing this file triggers .github/workflows/scrape_talks.yml, which geocodes
            `location` and auto-commits an updated talkmap/. Do not hand-edit talkmap/.
REMEMBER: also add this talk to the hand-curated lists in _pages/about.md and _pages/cv.md.
-->

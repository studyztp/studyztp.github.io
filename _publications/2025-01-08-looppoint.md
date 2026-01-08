---
title: "Accelerating the Simulation of Parallel Workloads using Loop-Bounded Checkpoints"
collection: publications
category: manuscripts
permalink: /publication/2025-01-08-looppoint-sampling
excerpt: "LoopPoint: A synchronization-agnostic loop-based sampling methodology that enables fast, accurate simulation of multi-threaded workloads via loop-bounded checkpoints."
date: 2025-01-08
venue: 'ACM Transactions on Architecture and Code Optimization (TACO)'
status: 'Under Review'
paperurl: ''
citation: 'Sabu, A., Qiu, Z., Patil, H., Liu, C., Heirman, W., Lowe-Power, J., & Carlson, T. E. (2025). Accelerating the Simulation of Parallel Workloads using Loop-Bounded Checkpoints. Under review at ACM TACO.'
---

## Abstract

Efficient simulation of multi-threaded workloads remains a critical challenge in computer architecture research. Existing sampling techniques often struggle with synchronization complexity and inter-thread dependencies. This work proposes **LoopPoint**, a synchronization-agnostic loop-based sampling methodology that enables fast, accurate simulation of multi-threaded workloads via loop-bounded checkpoints.

## Key Contributions

1. **Synchronization-Agnostic Sampling**: Provides loop-bounded checkpoints that efficiently handle synchronization and inter-thread communication without explicit synchronization point detection

2. **Performance Results**: Achieves up to **801× speedup** on SPEC CPU2017 with approximately **2.3% average runtime error** compared to full simulation

3. **Hardware Validation**: Introduces **ROIperf** for validating representative regions directly on silicon, enabling efficient hardware-based validation of sampling accuracy

4. **LoopPoint Extension**: Extends the prior LoopPoint paper published at HPCA with journal-level contributions and comprehensive evaluation on parallel workloads

## Research Impact

This work enables researchers to:
- Quickly simulate large-scale parallel workloads
- Validate sampling methodologies on real hardware
- Reduce simulation time for multi-threaded performance studies by orders of magnitude
- Better understand the behavior of parallel applications in computer architecture simulators

**Status**: Under review at ACM Transactions on Architecture and Code Optimization (TACO)

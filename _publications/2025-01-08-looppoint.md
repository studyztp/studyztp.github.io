---
title: "Accelerating the Simulation of Parallel Workloads using Loop-Bounded Checkpoints"
collection: publications
category: manuscripts
permalink: /publication/2025-01-08-looppoint-sampling
excerpt: "LoopPoint: A synchronization-agnostic loop-based sampling methodology that enables fast, accurate simulation of multi-threaded workloads via loop-bounded checkpoints (LoopPoint paper extension)."
date: 2025-01-08
venue: 'ACM Transactions on Architecture and Code Optimization (TACO)'
status: 'Under Review'
paperurl: ''
citation: TBD
---

## Abstract

Efficient sampled simulation of multi-threaded applications remains a long-standing challenge with significant implications for evaluating modern computing systems. Existing methodologies are either limited in speedup (Time-based Sampling) or restricted to specific synchronization types (BarrierPoint). Workload-specific techniques tend to be rigid with respect to region selection, which may limit the overall speedup.

In this work, we aim to solve these challenges and propose a novel sampling technique for multi-threaded applications, called LoopPoint, that is both agnostic to the type of synchronization primitives used and scales with the similarity exhibited by the application. The methodology combines several vital features, including (a) repeatable, up-front loop-based analysis of the workload, (b) a novel clustering approach to take into account run-time parallelism, and (c) the use of simulation markers to divide the execution into measurable chunks based on the amount of work done, even in the presence of spin-loops. LoopPoint identifies representative regions that can be simulated in parallel to achieve speedups of up to 801× for the train input set of the multi-threaded SPEC CPU2017 benchmarks with an average simulation error of just 2.33%.
We further propose ROIperf, a silicon based framework to enable rapid correlation of representative regions. Instead of long-running simulations, ROIperf allows for the performance measurement of full workloads and the representative regions directly on silicon.
This presents a practical methodology for large, realistic workloads where the prevailing simulation-based validation techniques are prohibitively slow. We demonstrate the efficacy of ROIperf across SPEC CPU2017 and NPB benchmark suites, showing strong correlation between hardware measurements and simulation predictions.

Extension of the LoopPoint paper published in HPCA 2022.
In this work, we demonstrate the full-system simulation of LoopPoint on gem5 with implementation details, propose ROIperf – a novel technique for sample validation, and release the representative executable checkpoints or ELFies of SPEC CPU2017 benchmarks.

**Status**: Under review at ACM Transactions on Architecture and Code Optimization (TACO)

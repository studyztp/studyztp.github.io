---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

📄 **[Download PDF CV](/files/Zhantong_Qiu_CV.pdf)**

Introduction
======
Computer architecture researcher focusing on computer system performance evaluation, simulation methodology, and hardware-software co-design for emerging applications. I build novel frameworks for fast, accurate, and portable computer system performance evaluation using sampled simulation. I tackle robotic applications on tiny robots and HPC workloads in datacenters through hardware-software co-design. I am a strong programmer and active contributor to production open-source simulators (e.g., gem5). I seek challenges in constrained systems and solve them with solutions that span multiple layers of the computer system stack.

Education
======
* Master of Science in Computer Science, University of California, Davis, Davis, California, Fall 2023 - Spring 2026 (expected)
* Visiting Student in Electrical and Computer Engineering, Cornell University, Ithaca, New York, Fall 2025 - Spring 2026
* Bachelor of Science in Computer Science and Engineering, University of California, Davis, Davis, California, Fall 2020 - Spring 2023

Publications
======
* **[Nugget: Portable Program Snippets](https://arxiv.org/abs/2509.02873)** (HPCA 2026). Zhantong Qiu, Mahyar Samani, Jason Lowe-Power. Introduced an LLVM IR-based sampling framework that converts long-running workloads into portable, binary/ISA-independent nuggets, enabling hardware-based interval analysis and reducing sampling overhead by over 500x vs. functional simulation; used to develop sampling methods and diagnose simulator modeling errors in gem5.
* **Accelerating the Simulation of Parallel Workloads using Loop-Bounded Checkpoints** (TACO 2025). Alen Sabu, Zhantong Qiu, Harish Patil, Changxi Liu, Wim Heirman, Jason Lowe-Power, Trevor E. Carlson. Paper extension of LoopPoint, a synchronization-agnostic loop-based sampling method with loop-bounded checkpoints for fast, accurate multi-threaded simulation, delivering up to 801x speedup on SPEC CPU2017 with about 2.3% average runtime error; released a gem5 module for full-system simulation and introduced ROIperf to validate representative regions directly on silicon.

Talks and Tutorials
======
* HPCA 2026 - Nugget: Portable Program Snippets (Main Conference, Sydney, Australia).
* CGO 2026 - Nugget with LLVM infrastructure (LLVM-CGO 2026 Workshop, Sydney, Australia).
* gem5 Bootcamp 2024 - Week-long hands-on training on the gem5 simulator (UC Davis, CA).
* HPCA 2023 - LoopPoint using Sniper and gem5 (LoopPoint Tutorial, Montreal, Canada).
* ISCA 2023 - Technique talk on full-system sampling support in gem5 (gem5 Workshop, Orlando, FL).

Research Experience
======
* June 2023 - Present: Graduate Researcher, DArchR Lab, UC Davis
  * Advisor: Jason Lowe-Power
  * **Nugget (LLVM IR sampling)**
    - Designed and implemented a cross-platform, architecture-independent sampling framework at the LLVM IR level; supports rapid interval analysis, native execution for validation, and cross-ISA simulation.
    - Evaluated Nugget on real hardware platforms with diverse performance characteristics (e.g., Ampere Altra) and in the gem5 simulator to validate fidelity and portability.
    - Analyzed a diverse set of workloads (SPEC CPU2017, NPB, LSMS) to demonstrate robustness across CPU, HPC, and scientific applications.
  * **Accelerating the Simulation of Parallel Workloads using Loop-Bounded Checkpoints**
    - Co-led methodology and implementation to validate LoopPoint samples on gem5.
  * **SPEAR: Scalable Power and Energy Analysis and Performance Tools for Frontier**
    - Collaborating with researchers at Oak Ridge National Laboratory and the University of Wisconsin-Madison to apply sampling techniques (e.g., Nugget) to bound significant execution regions for GPU+CPU high-performance applications on Frontier.
    - Characterizing GPU+CPU high-performance applications to develop simulation methodologies that accelerate large-scale system simulation (e.g., Frontier).
  * **[gem5 contributions](https://github.com/gem5/gem5/commits?author=studyztp)**
    - Ongoing upstream contributions since 2022 to full-system sampling support and related simulation features in gem5; author of 50 commits (public history).

* August 2025 - Present: Visiting Student, Computer Systems Laboratory, Cornell University
  * Advisor: Christopher Batten
  * **Agile Robotic Hardware-Software Co-Design**
    - Developing a closed-loop, multi-robot evaluation framework integrating robotics simulators and architecture simulators; enables parallel per-robot simulation and decouples from a specific ISA/simulator to broaden studies (e.g., ISA extensions).
  * **[Accurate STM32G4 Board in gem5](https://github.com/studyztp/gem5/tree/studyztp/ART-cache)**
    - Building an accurate STM32G4 MCU model in gem5 (Arm M-profile). Implemented the ART (Adaptive Real-Time) accelerator to improve Flash access latency; planning to upstream core M-profile components (e.g., NVIC).

* June 2022 - June 2023: Undergraduate Researcher, DArchR Lab, UC Davis
  * Advisor: Jason Lowe-Power
  * **SimPoint**
    - Implemented SimPoint support in the gem5 stdlib and ran SPEC CPU2006 experiments using SimPoint.
  * **LoopPoint**
    - Implemented LoopPoint support in system-emulation and full-system modes in gem5; added a generalized PC-execution counter to track occurrences of specific PCs.

Course Projects
======
* **[CXL Shared Memory Filesystem Optimization](https://github.com/orgs/ECS-289D/repositories)**
  - Investigated application needs in a CXL shared-memory system and improved the FAMFS framework with more efficient allocation/deallocation and zero-copy operations to avoid redundant copies.
* **[Limitations of Disaggregated Memory and Innovations](https://github.com/studyztp/my-course-paper/blob/main/Limitations_of_Disaggregated_Memory_and_Innovations.pdf)**
  - Analyzed limitations of disaggregated memory and proposed a hardware-software co-designed page management approach.
* **[CUDA Microbenchmarks](https://github.com/studyztp/CUDA_microbenchmarks.git)**
  - Developed configurable microbenchmarks to measure shared-memory latency and memory-scaling behavior on GPUs.
* **RISC-V Operating System**
  - Built a simple RISC-V OS on the UC Davis RISC-V Console Simulator for a course project.

Teaching Experience
======
* WQ 2024: ECS 154B Computer Architecture, Teaching Assistant
  - Led weekly discussion sections and office hours; created assignment material on Chisel-based CPU model (DINO CPU).

Organizations and Service
======
* **Founder of Computer Systems Seminar at UC Davis**
  - Organized weekly speaker series with 12+ talks from academia and industry (ongoing).
* **HPCA 2026 Artifact Evaluation Reviewer**
  - Helped reviewing the artifact of the accepted paper.

Skills
======
* **Programming Languages**: C/C++, Python, Bash, CUDA, Assembly, LaTeX
* **Hardware Description Languages**: Chisel
* **System Evaluation Tools**: gem5, QEMU
* **Profiling and Instrumentation**: LLVM passes, DynamoRIO, Valgrind, Linux perf, PAPI
* **Other Linux Tools**: cpuset, CRIU, cgroups, Docker
* **Compilers**: GCC/G++, GFortran, Clang/LLVM
* **Languages**: English, Cantonese, Mandarin

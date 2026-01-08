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

Education
======
* Master of Science in Computer Science, University of California, Davis, Fall 2023 – Spring 2026 (expected)
* Visiting Student in Electrical and Computer Engineering, Cornell University, Fall 2025 – Spring 2026
* Bachelor of Science in Computer Science and Engineering, University of California, Davis, Fall 2020 – Spring 2023

Work experience
======
* June 2023 – Present: Graduate Researcher
  * DArchR Lab, UC Davis
  * Advisor: Professor Jason Lowe-Power
  * **[Nugget (LLVM IR sampling)](/publication/2026-02-22-nugget)**
    - Designed and implemented a cross-platform, architecture-independent sampling framework at the LLVM IR level; supports rapid interval analysis, native execution for validation, and cross-ISA simulation.
    - Evaluated Nugget on real hardware platforms with diverse performance characteristics (e.g., Ampere Altra) and in the gem5 simulator to validate fidelity and portability.
    - Analyzed a diverse set of workloads (SPEC CPU2017, NPB, LSMS) to demonstrate robustness across CPU, HPC, and scientific applications.
  * **[Accelerating the Simulation of Parallel Workloads using Loop-Bounded Checkpoints](/publication/2025-01-08-looppoint-sampling)**
    - Co-led methodology and implementation to validate LoopPoint samples on gem5; under journal review.
  * **[gem5 contributions](https://github.com/gem5/gem5/commits?author=studyztp)**
    - Ongoing upstream contributions since 2022 to full-system sampling support and related simulation features in gem5; author of 50+ commits.

* August 2025 – Present: Visiting Student
  * Computer Systems Laboratory, Cornell University
  * Advisor: Professor Christopher Batten
  * **Agile Robotic Hardware-Software Co-Design**
    - Developing a closed-loop, multi-robot evaluation framework integrating robotics simulators and architecture simulators; enables parallel per-robot simulation and decouples from a specific ISA/simulator to broaden studies (e.g., ISA extensions).
  * **Accurate STM32G4 Board in gem5**
    - Building an accurate STM32G4 MCU model in gem5 (Arm M-profile). Implemented the ART (Adaptive Real-Time) accelerator to improve Flash access latency; planning to upstream core M-profile components (e.g., NVIC).

* June 2022 – June 2023: Undergraduate Researcher
  * DArchR Lab, UC Davis
  * Advisor: Professor Jason Lowe-Power
  * **SimPoint**
    - Implemented SimPoint support in the gem5 stdlib and ran SPEC CPU2006 experiments using SimPoint.
  * **LoopPoint**
    - Implemented LoopPoint support in system-emulation and full-system modes in gem5; added a generalized PC-execution counter to track occurrences of specific PCs.

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>
  
Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

Service and leadership
======
* **Teaching Experience**: WQ 2024 ECS 154B: Computer Architecture Teaching Assistant
  - Led weekly discussion sections and office hours; created assignment material on Chisel-based CPU model (DINO CPU).

* **Founder, Computer Systems Seminar at UC Davis**
  - Organized weekly speaker series with 12+ talks from academia and industry (ongoing).

* **Active contributor to gem5 open-source simulator**
  - 50+ commits on full-system sampling and simulation features.

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

Skills
======
* **Programming Languages**: C/C++, Python, Bash, CUDA, Assembly, LaTeX
* **Hardware Description Languages**: Chisel
* **System Evaluation Tools**: gem5, QEMU
* **Profiling & Instrumentation**: LLVM passes, DynamoRIO, Valgrind, Linux perf, PAPI
* **Linux Tools**: cpuset, CRIU, cgroups, Docker
* **Compilers**: GCC/G++, GFortran, Clang/LLVM
* **Languages**: English (native), Cantonese (native), Mandarin (professional)

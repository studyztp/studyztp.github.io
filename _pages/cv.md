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
  * Duties included: Designed and implemented Nugget LLVM IR sampling framework; validated LoopPoint samples in gem5; made 50+ upstream contributions to gem5
  * Advisor: Professor Jason Lowe-Power

* August 2025 – Present: Visiting Student
  * Computer Systems Laboratory, Cornell University
  * Duties included: Developing closed-loop multi-robot evaluation framework; building accurate STM32G4 MCU model in gem5
  * Advisor: Professor Christopher Batten

* June 2022 – June 2023: Undergraduate Researcher
  * DArchR Lab, UC Davis
  * Duties included: Implemented SimPoint and LoopPoint support in gem5; added generalized PC-execution counter for tracking
  * Advisor: Professor Jason Lowe-Power
  
Skills
======
* **Programming Languages**: C/C++, Python, Bash, CUDA, Assembly, LaTeX
* **Hardware Description Languages**: Chisel
* **System Evaluation Tools**: gem5, QEMU
* **Profiling & Instrumentation**: LLVM passes, DynamoRIO, Valgrind, Linux perf, PAPI
* **Linux Tools**: cpuset, CRIU, cgroups, Docker
* **Compilers**: GCC/G++, GFortran, Clang/LLVM
* **Languages**: English (native), Cantonese (native), Mandarin (professional)

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
* Founder, Computer Systems Seminar at UC Davis - Organized weekly speaker series with 12+ talks from academia and industry (ongoing)
* Active contributor to gem5 open-source simulator - 50+ commits on full-system sampling and simulation features

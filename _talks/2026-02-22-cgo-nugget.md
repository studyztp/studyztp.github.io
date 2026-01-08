---
title: "Nugget with LLVM Infrastructure - LLVM-CGO-2026 Technique Talk"
collection: talks
type: "Workshop"
permalink: /talks/2026-llvm-cgo-nugget
venue: "LLVM-CGO-2026 Workshop"
date: 2026-02-22
location: "Sydney, Australia"
---

## Overview

This technique talk presents the LLVM infrastructure and compiler-based aspects of **Nugget**, an LLVM IR-based sampling framework for computer system performance evaluation.

## Presentation Focus

- LLVM IR-level sampling framework design
- Compiler instrumentation techniques for efficient sampling
- Cross-ISA portability at the IR level
- Integration with LLVM compiler infrastructure
- Implementation details and best practices
- Real-world applications in computer architecture research

## Technical Highlights

- IR-level unit of work for binary independence
- Compiler-based instrumentation vs. simulator-based approaches
- Rapid interval analysis on real hardware
- Cross-platform portability and reusability

## Key Benefits

- Hundreds of times faster sampling than functional simulation
- Portable across different ISAs and microarchitectures
- Direct validation on real hardware
- Enables diagnosis of simulator inaccuracies

## Related Publication

For complete technical details, see: **[Nugget: Portable Program Snippets](/publication/2026-02-22-nugget)**

Learn more: [https://arxiv.org/abs/2509.02873](https://arxiv.org/abs/2509.02873)

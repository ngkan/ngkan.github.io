---
title: "MiniFormalizer: Agentic Autoformalization in Lean 4"
date: 2026-11-13
draft: false
layout: "page"
description: "An agentic system for coordinating agents that write, check, and refine Lean 4 proofs."
showDate: false
showReadingTime: false
showWordCount: false
showComments: false
showPagination: false
projectURL: "https://github.com/ngkan/miniformalizer/tree/master"
---

(The following content is AI-generated.)

[MiniFormalizer](https://github.com/ngkan/miniformalizer/tree/master) is a prototype for experimenting with automated mathematical formalization in Lean 4. It brings together agents that propose proofs, tools that check them, and workflows that use the resulting feedback to try again.

The interesting part is the loop between a proposed argument and a checked proof. A plausible explanation can still leave gaps; Lean makes those gaps concrete. The prototype explores how to organize that feedback when a task needs more than a single proof attempt.

## What it explores

The repository includes several approaches to organizing proof work. One is a blueprint-based workflow: represent a proof through smaller statements and their dependencies, attempt those pieces, and refine the structure when progress stalls. It can run multiple node provers concurrently and reattach checked proof bodies as the blueprint changes.

There is also a project-level workflow that visits Lean files in dependency order, attempts unfinished proofs, and checks the resulting files. It tracks remaining `sorry` placeholders alongside verification errors, so removing a placeholder alone does not count as a successful formalization.

The supporting tools include Lean checking through Pantograph, configurable models and agents, and tracing for inspecting runs. Together, these make the repository a place to compare workflows and investigate where proof attempts fail.

## Current state

This is an experimental prototype. The repository contains example outputs for Putnam 2025 problems, including failed attempts. Those files are useful starting points for inspection, but they are not a substitute for a reproducible evaluation or a claim that every problem is solved.

[Explore the code on GitHub](https://github.com/ngkan/miniformalizer/tree/master).

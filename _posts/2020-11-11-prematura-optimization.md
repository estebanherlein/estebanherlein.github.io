---
title: "Premature optimization"
categories:
  - Blog
tags:
  - Software Design Anti-Patterns
  - Methodological Anti-Patterns
---

A phrase used to describe a situation where a programmer lets performance considerations affect the design of a piece of code. 

This can result in a design that is not as clean as it could have been or code that is incorrect, because the code is complicated by the optimization and the programmer is distracted by optimizing.

When deciding whether to optimize a specific part of the program, Amdahl's Law should always be considered: 

>the impact on the overall program depends very much on how much time is actually spent in that specific part, which is not always clear from looking at the code without a performance analysis.

A better approach is therefore to design first, code from the design and then profile/benchmark the resulting code to see which parts should be optimized. 

A simple and elegant design is often easier to optimize at this stage, and profiling may reveal unexpected performance problems that would not have been addressed by premature optimization.

In practice, it is often necessary to keep performance goals in mind when first designing software, but the programmer balances the goals of design and optimization.

Modern compilers and operating systems are so efficient that the intended performance increases often fail to materialize. 

As an example, caching data at the application level that is again cached at the operating system level does not yield improvements in execution. Even so, it is a rare case when the programmer will remove failed optimizations from production code.

It is also true that advances in hardware will more often than not obviate any potential improvements, yet the obscuring code will persist into the future long after its purpose has been negated. 
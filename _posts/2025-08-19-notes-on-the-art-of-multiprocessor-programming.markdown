---
layout: post
title:  "Notes on The Art of Multiprocessor Programming"
date:   2025-08-19 22:00:00 +0530
categories: concurrency
---

[Book Review][br] by John Viega from Crash Override.

Multiprocessor programming is closely related to Performance Engineering.
This [YouTube playlist][yt-pe] by MIT on Performance Engineering is good.

### Introduction

The producer-consumer problem appears in all parallel and distributed systems.
A fault tolerant distributed system that has various components wanting to
access shared resources should ensure mutual exclusion, deadlock free, 
starvation free, and wait free access. Another problem is the readers-writers
problem. It is particularly useful to design wait-free solutions. An example
is a background thread capturing a backup should not cause the main thread to
wait for it to finish.

### Mutual Exclusion

Several algorithms that solve the mutual exclusion problem are discussed. The
Peterson Lock algorithm and Lamport's Bakery algorithm are noteworthy.

### Concurrent Objects

Linearizability and consistency models are two big concepts introduced in this
chapter. Here are some more good resources to understand these concepts:

- [Consistency models][cm] page on Jepsen website.
- [This PDF][tp] on Chinese University of HongKong website.
- A research paper titled [On the Nature of Progress][nop] by the authors of
this book.


### Foundations of Shared Memory

This chapter focuses on constructing safe registers for co-ordinating
overlapping memory accesses. A collection of Single Reader Single Writer
Registers (SRSW) and used to construct MRSW and MRMW registers. Ideas
related to lock-free and wait-free co-ordination are also discussed. 


[br]: https://h4x0r.org/futex/
[yt-pe]: https://www.youtube.com/playlist?list=PLUl4u3cNGP63VIBQVWguXxZZi0566y7Wf
[cm]: https://jepsen.io/consistency/models
[tp]: https://mobitec.ie.cuhk.edu.hk/iems5730Spring2024/static_files/slides/ConsistencyModelsESTR4316Spring2024.pdf
[nop]: https://dspace.mit.edu/bitstream/handle/1721.1/73900/Shavit_On%20the%20nature%20of%20progress.pdf

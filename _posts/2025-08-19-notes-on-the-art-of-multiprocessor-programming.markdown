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


[br]: https://h4x0r.org/futex/
[yt-pe]: https://www.youtube.com/playlist?list=PLUl4u3cNGP63VIBQVWguXxZZi0566y7Wf

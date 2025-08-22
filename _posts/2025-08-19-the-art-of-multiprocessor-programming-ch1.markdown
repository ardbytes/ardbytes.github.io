---
layout: post
title:  "The Art of Multiprocessor Programming - Chapter 1 Notes"
date:   2025-08-19 22:00:00 +0530
categories: concurrency
---

[Book Review][br] by John Viega from Crash Override.

The producer-consumer problem appears in all parallel and distributed systems.
A fault tolerant distributed system that has various components wanting to
access shared resources should ensure mutual exclusion, deadlock free, 
starvation free, and wait free access. Another problem is the readers-writers
problem. It is particularly useful to design wait-free solutions. An example
is a background thread capturing a backup should not cause the main thread to
wait for it to finish.


[br]: https://h4x0r.org/futex/

---
layout: post
title:  "DDIA References"
date:   2025-09-18 11:00:00 +0530
categories: concurrency
---

One of the good things about The DDIA book is the References section at the end
of each chapter. This blog post documents my notes on reading some of the
referenced items.

### Chapter 1: Reliable Scalable and Maintainable Applications

Reliability is the ability of the system to continue to provide service even
during system faults. Handling faults in a system make in reliable. To be
able to handle system faults we must first anticipate them. The
[Principles of Software Engineering, Part 1][pose-p1] post by Nathan Marz
discusses how Engineering is different from Programming. In Programming, the
set of inputs are deterministic. In Engineering, they are not. A big part of
being a good Engineer is having the ability to anticipate different conditions
that the system would be subjected to and build capabilities in the system to
handle such conditions gracefully.

Scalability is the ability of the system to deliver acceptable performance
even in situations of increased load. Section 2.3 of the Amazon [Dynamo][dyn]
research paper discusses the design considerations for achieving high
scalability. Section 4.2 describes [consistent hashing][ch] which is used for
data paritioning and replication. Section 4.4 describes [vector clocks][vc]
which is used for data consistency.

Measuring latency is important to understand how systems are able to cope
with load. Gil Tene's talk on [How NOT to Measure Latency][gt] provide numerous
hints on [monitoring the metrics][mtm] that are most useful in analyzing the
behaviour of your systems.

[pose-p1]: http://nathanmarz.com/blog/principles-of-software-engineering-part-1.html
[dyn]: https://www.allthingsdistributed.com/files/amazon-dynamo-sosp2007.pdf
[ch]: https://www.youtube.com/watch?v=UF9Iqmg94tk
[vc]: https://www.youtube.com/watch?v=b2Tud5Kkue8
[gt]: https://www.youtube.com/watch?v=lJ8ydIuPFeU
[mtm]: https://latencytipoftheday.blogspot.com/2014/06/latencytipoftheday-q-whats-wrong-with_21.html

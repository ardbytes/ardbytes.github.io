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
being a good Engineer is having the ability to **anticipate** different
conditions that the system would be subjected to and build capabilities in
the system to handle such conditions gracefully.

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

Maintainability of a system affects its reliability and scalability. [Out of the
Tar Pit][oot-tp] discusses how state is the main culprit in making systems
complex and hard to maintain. In [The Big OOPs][tbo] talk, Casey says that
"compile-time hierarchy of encapsulation that matches the domain model" is the
dominant way of writing object oriented programs. This makes them hard to
maintain. Casey further notes that **discriminated unions** are more useful
than virtual functions. However, Bjarne did not include it into C++ because
he thought that it broke modularity.

### Chapter 2: Data Models and Query Languages

The relational data model dominates the other data models by a wide margin. On
a related note, please [read][wg1] [these][wg2]. The first paper provides a
summary of 35 years of data model proposals, grouped into 9 different eras. I
found the summary after describing each era very informative. The second paper
is a revision of the first paper after a gap of two decades. The discussion
about vector databases and column-oriented databases are noteworthy.

### Chapter 3: Storage and Retrieval

Hash table is a commonly used data structure for fast retrieval of stored data.
Watch the [Hash Table Internals][hti] playlist by Arpit, then work through the
[Write a Hash Table in C][htic] tutorial by James. Also I enjoyed reading the
[uthash][uth] code by Troy.

[ch]: https://www.youtube.com/watch?v=UF9Iqmg94tk
[dyn]: https://www.allthingsdistributed.com/files/amazon-dynamo-sosp2007.pdf
[gt]: https://www.youtube.com/watch?v=lJ8ydIuPFeU
[hti]: https://www.youtube.com/playlist?list=PLsdq-3Z1EPT2UnueESBLReaVSLIo_BuAc
[htic]: https://github.com/jamesroutley/write-a-hash-table
[mtm]: https://latencytipoftheday.blogspot.com/2014/06/latencytipoftheday-q-whats-wrong-with_21.html
[oot-tp]: https://curtclifton.net/papers/MoseleyMarks06a.pdf
[pose-p1]: http://nathanmarz.com/blog/principles-of-software-engineering-part-1.html
[tbo]: https://www.youtube.com/watch?v=wo84LFzx5nI
[uth]: https://github.com/troydhanson/uthash
[vc]: https://www.youtube.com/watch?v=b2Tud5Kkue8
[wg1]: http://mitpress2.mit.edu/books/chapters/0262693143chapm1.pdf
[wg2]: https://db.cs.cmu.edu/papers/2024/whatgoesaround-sigmodrec2024.pdf

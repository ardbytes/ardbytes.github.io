---
layout: post
title:  "DDIA Notes"
date:   2025-09-18 11:00:00 +0530
categories: books
---

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

LSM Trees and B-Trees are also commonly used [data][ds1]-[structures][ds2] for
indexing stored data.

### Chapter 4: Encoding and Evolution

The data stored by applications need to evolve with changing application
requirements. In this regard, compatibility becomes important.

1. Backward Compatibility: Newer code can read data written by older code.
2. Forward Compatibility: Older code can read data written by newer code.

JSON, XML, MessagePack, and Thrift are some of the popular encoding formats.
Asynchronous message passing is a widely used technique to exhange data
between two processes. [This article][mqus] by Leandro describes a simple yet
interesting approach to buidling a message broker using only two Unix signals.

### Chapter 5: Replication

To avoid single point of failure multiple database nodes are needed. A single
node accepts writes with multiple replicated nodes handling reads. When this
write-accepting node fails, then one of the readers must be promoted to accept
writes. The write-accepting node is called a leader.  The Improving MySQL
Cluster Uptime [article][ua] describes how automatic failover helped in
improving relability of Uber's database cluster.

### Chapter 6: Partitioning

While replication improves reliability of a system, partitioning improves its
scalability. The book discusses horizontal partitioning, that is, distributing
the rows of a table onto multiple nodes. However, vertical partitioning is also
possible as described in the [article][pg] titled Partitioning Github's
relational databases to handle scale. This involves splitting the tables of a
database schema onto multiple nodes.

[ch]: https://www.youtube.com/watch?v=UF9Iqmg94tk
[ds1]: https://www.youtube.com/watch?v=oWgLjhM-6XE&list=PLrS21S1jm43igE57Ye_edwds_iL7ZOAG4
[ds2]: https://www.youtube.com/watch?v=xwI5OBEnsZU
[dyn]: https://www.allthingsdistributed.com/files/amazon-dynamo-sosp2007.pdf
[gt]: https://www.youtube.com/watch?v=lJ8ydIuPFeU
[hti]: https://www.youtube.com/playlist?list=PLsdq-3Z1EPT2UnueESBLReaVSLIo_BuAc
[htic]: https://github.com/jamesroutley/write-a-hash-table
[mqus]: https://leandronsp.com/articles/you-dont-need-kafka-building-a-message-queue-with-only-two-unix-signals
[mtm]: https://latencytipoftheday.blogspot.com/2014/06/latencytipoftheday-q-whats-wrong-with_21.html
[oot-tp]: https://curtclifton.net/papers/MoseleyMarks06a.pdf
[pg]: https://github.blog/engineering/infrastructure/partitioning-githubs-relational-databases-scale/
[pose-p1]: http://nathanmarz.com/blog/principles-of-software-engineering-part-1.html
[tbo]: https://www.youtube.com/watch?v=wo84LFzx5nI
[ua]: https://www.uber.com/en-IN/blog/improving-mysql-cluster-uptime-part1/
[uth]: https://github.com/troydhanson/uthash
[vc]: https://www.youtube.com/watch?v=b2Tud5Kkue8
[wg1]: http://mitpress2.mit.edu/books/chapters/0262693143chapm1.pdf
[wg2]: https://db.cs.cmu.edu/papers/2024/whatgoesaround-sigmodrec2024.pdf

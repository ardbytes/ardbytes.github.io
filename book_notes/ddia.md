Here are the notes taken while reading [Designing Data-Intensive Applications][ddia]

### Chapter 1: Reliable, Scalable, and Maintainable Applications

Applications can be reliable, scalable, and maintainable if different data sources are stored in different databases.
For example, user data and telemetry data should not be stored on the same database server.

Later chapters of the book discuss:

1. Techniques for building reliable systems from unreliable parts.
2. Building blocks and patterns of scalable architectures.
3. Abstractions that allows extracting parts of a large system into well-defined, reusable components.

### Chapter 2: Data models and Query languages

Relational, document, and graph data models are widely used today.

Data models widely used today:

1. Relational ( good for representing one-to-many and many-to-one relations )
2. Document ( good for representing one-to-many relations )
3. Graph ( good for highly related data )

The data model that best fits our application depends on the type of data we need to store and their access patterns ( relations ).
Later chapters of the book discuss how to find out the data model that best fits the requirements of our application.

> Study about the full text search data model.

### Chapter 3: Storage and Retrieval

Understanding how storage engines store and retrieve data is necessary for selecting one that suites the needs of an application.
This knowledge is also useful for tuning selected storage engine to improve its performance. SSTables, Hash indexes, and B-Trees
are some of the widely used data structures in storage engines.

For scalability, it is wise to use separate database servers for transaction processing and analytics. Indexing improves performance
of transaction processing applications and encoding improves performance of analytics applications.

### Chapter 4: Encoding and Evolution

The choice of encoding affects how in-memory data structures are represented as bytes on a network connection or inside a disk.
Choice of encoding impacts the amount of storage used and the scope for future evolution of the encoded data. Data when encoded
according to a schema ensures correctness.

Applications will be expected to process new data as requirements arise. Schema evolution demands backward compatibility ( new code can
read old data ) and forward compatibility ( old code can read new data ) from the encoding standard.

### Chapter 5: Replication

Replication becomes necessary when users expect require high availability, low latency, and tolerance to hardware and network failures.
Applications handling replicated ( distributed ) data must resolve issues arising from concurrent access and replication lag.

### Chapter 6: Partitioning

Partitioning complements Replication in making the system more scalable and reliable ( at the cost of increasing maintenance ). This chapter
discusses approaches to store and access data that are partitioned across several nodes. Concept of service discovery is also mentioned.
Of special interest is the scenario where a single user action requires storing data in several partitions. What happens when writing to
some partitions succeed and others fail?

### Chapter 7: Transactions

A single database serves many users. Things become complicated when multiple users attempt to modify values at the same time. Unchecked updates
can lead to the whole database being inconsistent and thus worthless. To maintain consistency transactions are necessary. A database can be
configured to run in one of the several isolation levels, and it must ensure that data remains consistent as per the configured
isolation level.

> [This article][mvcc-isolation] describes using MVCC to implement isolation levels.

### Chapter 8: the Trouble with Distributed Systems

When nodes communicate only through message passing over a network many issues may occur:

1. Node could be alive but connectivity to the node may be broken.
2. Node can crash without the system knowing what it was upto.
3. Skewed clocks may mess up with ordering of events.
4. Process pauses along with failover mechanisms may cause data inconsistency. 

To handle these issues, it is necessary to develop a model of the system, and develop algorithms in accordance to the specified model.

### Chapter 9: Consistency and Consensus

Many of the problems discussed in previous chapters, like performing a failover of a leader, enforcing uniqueness constraints, and atomic transaction
commit can be solved by deploying a service that implements a consensus algorithm. Zookeeper provides consensus while also supporting fault tolerance.
From next chapter onwards focus will be on building practical applications based on the theory discussed so far in this book.

[ddia]: https://dataintensive.net/
[mvcc-isolation]: https://notes.eatonphil.com/2024-05-16-mvcc.html

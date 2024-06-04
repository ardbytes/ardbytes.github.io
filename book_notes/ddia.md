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

[ddia]: https://dataintensive.net/

Here are the notes taken while reading [Designing Data-Intensive Applications][ddia]

### Chapter 1: Reliable, Scalable, and Maintainable Applications

Applications can be reliable, scalable, and maintainable if different data sources are stored in different databases.
For example, user data and telemetry data should not be stored on the same database server.

Later chapters of the book discuss:

1. Techniques for building reliable systems from unreliable parts.
2. Building blocks and patterns of scalable architectures.
3. Abstractions that allows extracting parts of a large system into well-defined, reusable components.

[ddia]: https://dataintensive.net/

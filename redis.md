# REDIS

### NOTES

- Redis is an in-memory key-value pair database.
- A multi-model database supporting a varietly of database paradigms with addon modules.
  - RediSearch: A query and indexing engine for Redis, providing secondary indexing, full-text search, vector similarity search and aggregations.
  - RedisGraph: A graph database as a Redis module
  - RedisBloom: Probabilistic Datatypes Module for Redis
  - RedisAI: a Redis module for executing Deep Learning/Machine Learning models and managing their data.
  - RedisJSON: Allows storing, updating and fetching JSON values from Redis keys (documents).
  - RedisTimeSeries: Redis Stack (specifically, its RedisTimeSeries module) adds a time series data structure to Redis.
- Redis use cases:
  - Caching
  - User Session Management
  - Rate Limiter
  - Distributed Locks
  - Gaming Leaderboards
- Redis is a single threaded database
- Redis uses IO multiplexing to concurrently handle multiple requests in a single thread.
- It is not uncommon to have multiple redis instances in a single server to utilize all CPU cores.
- Redis also supports data persistence to disk but in case of a crash/restart it would take too long to restore (not practical in a distrubuted production environment), replication is used instead where another redis instance will take over.
- @TODO: What is a distributed lock?
- #### Modules
  - In Redis, modules are dynamic extensions that allow you to add new functionality to the database server. These modules enable you to extend Redis by introducing new data types, commands, and behaviors. 
  - Some examples of popular Redis modules include:
    - RediSearch: Adds full-text search capabilities to Redis.
    - RedisGraph: Provides graph database functionality within Redis.
    - RedisTimeSeries: Adds time-series data storage and operations to Redis.
    - Bloom Filter: Implements probabilistic data structures like Bloom filters in Redis.

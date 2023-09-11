# REDIS

### NOTES

- Redis is an in-memory key-value pair database.
- Redis use cases:
  - Caching
  - User Session Management
  - Rate Limiter
  - Distributed Locks
  - Gaming Leaderboards
- Redis is a single threaded database
- Redis uses IO multiplexing to currently handle requests in a single thread.
- It is not uncommon to have multiple redis instances in a single server to utilize all CPU cores.
- What is a distributed lock?
- Redis also supports data persistence to disk but in a case of a crash/restart it would take too long to restore (not practical in a distrubuted production environment), replication is used instead where a another redis instance will take over.

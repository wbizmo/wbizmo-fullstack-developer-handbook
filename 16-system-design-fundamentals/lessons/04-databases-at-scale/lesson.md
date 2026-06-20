# Lesson 04: Databases At Scale

## Learning Objectives

By the end of this lesson you should be able to:

- Explain why databases become bottlenecks.
- Understand read-heavy and write-heavy workloads.
- Understand indexes and query optimization.
- Explain connection pooling.
- Explain read replicas.
- Understand replication lag.
- Understand partitioning and sharding.
- Understand failover, backups and recovery.
- Design database scaling strategies for real backend systems.

---

## Introduction

Many applications start with one database.

At the beginning, this is fine.

Example:

    Fastify API
        |
        v
    PostgreSQL

This works for:

- small traffic
- small data
- few users
- simple queries

But as the system grows, the database often becomes the hardest component to scale.

Why?

Because the database is responsible for:

- storing data
- reading data
- updating data
- enforcing constraints
- maintaining indexes
- handling transactions
- serving many connections

Application servers can usually be duplicated easily.

Databases are more difficult because they hold state.

---

## Why Databases Become Bottlenecks

An API server can be stateless.

That means:

    API1
    API2
    API3

can all process requests independently.

But a database stores shared truth.

Example:

    users
    payments
    files
    contracts
    workflows
    jobs

All application servers may depend on the same database.

Architecture:

                Users
                  |
                  v
            Load Balancer
                  |
        ---------------------
        |         |         |
        v         v         v
      API1      API2      API3
        \         |        /
          \       |      /
            v     v    v
             PostgreSQL

If PostgreSQL becomes overloaded, adding more API servers may not solve the problem.

The database becomes the bottleneck.

---

## Common Database Bottlenecks

Common bottlenecks include:

- slow queries
- missing indexes
- too many connections
- large table scans
- lock contention
- heavy writes
- insufficient memory
- disk I/O pressure
- poor schema design
- inefficient joins

A scalable system needs to identify which bottleneck actually exists.

Guessing is dangerous.

Measure first.

---

## Read-Heavy vs Write-Heavy Workloads

Not all database workloads are the same.

### Read-Heavy Systems

Examples:

- blog platforms
- documentation sites
- product catalogs
- dashboards
- public APIs

Most operations are:

    SELECT

Read-heavy systems can often scale with:

- caching
- read replicas
- indexes
- materialized views

### Write-Heavy Systems

Examples:

- payment processing
- analytics ingestion
- logging systems
- chat applications
- workflow execution engines

Many operations are:

    INSERT
    UPDATE
    DELETE

Write-heavy systems are harder to scale because writes usually need stronger consistency.

---

## Database Performance Metrics

Important database metrics include:

### Query Latency

How long queries take.

Example:

    5ms
    50ms
    500ms
    5s

### Throughput

How many queries the database handles per second.

Example:

    500 queries/sec

### Connection Count

How many clients are connected.

### Lock Wait Time

How long queries wait for locks.

### Cache Hit Ratio

How often requested data is served from memory instead of disk.

### Disk I/O

How much reading/writing happens on disk.

### CPU Usage

High CPU may indicate expensive queries.

---

## Indexes

Indexes help databases find records faster.

Without an index:

    Scan every row

With an index:

    Jump to matching rows

Example:

    SELECT *
    FROM users
    WHERE email = 'ada@example.com';

If email is indexed, this query is much faster.

Create index:

    CREATE INDEX idx_users_email
    ON users(email);

---

## Good Index Candidates

Good candidates:

- email
- username
- foreign keys
- frequently searched columns
- frequently sorted columns

Examples:

    users.email
    api_keys.prefix
    files.owner_id
    workflows.workspace_id
    transactions.created_at

---

## Bad Index Candidates

Bad candidates:

- rarely queried columns
- columns with very low uniqueness
- columns updated very frequently
- huge text fields

Indexes are not free.

They improve reads but add overhead to writes.

Every insert, update or delete may need to update indexes.

---

## Query Optimization

Bad query:

    SELECT *
    FROM transactions;

Better:

    SELECT id, amount, created_at
    FROM transactions
    WHERE user_id = 1
    ORDER BY created_at DESC
    LIMIT 50;

Why better?

- selects only needed columns
- filters by user
- sorts intentionally
- limits result size

---

## Avoid SELECT *

`SELECT *` can be expensive.

It returns every column.

This may include:

- large text fields
- JSON blobs
- unused data
- sensitive data

Prefer selecting only what is needed.

---

## Pagination

Never return massive datasets at once.

Bad:

    GET /transactions

returns:

    1,000,000 records

Good:

    GET /transactions?page=1&limit=50

SQL:

    SELECT id, amount, created_at
    FROM transactions
    ORDER BY created_at DESC
    LIMIT 50
    OFFSET 0;

For very large datasets, cursor pagination is often better than offset pagination.

---

## Offset Pagination Problem

Offset pagination:

    OFFSET 100000

can become slow because the database still scans/skips many rows.

Cursor pagination:

    WHERE created_at < last_seen_created_at
    LIMIT 50

is usually more efficient for large tables.

---

## Connection Pooling

Every database connection uses resources.

If every request opens a new database connection:

    API request
        |
        v
    New DB connection

the database can become overloaded.

Connection pooling reuses connections.

Architecture:

    API
     |
     v
    Pool
     |
     v
    Database

Instead of creating thousands of new connections, the application reuses a controlled number.

---

## Why Connection Pools Matter

Without pooling:

- too many connections
- memory pressure
- database overload
- slow responses

With pooling:

- controlled access
- better resource usage
- improved stability

Common pool settings include:

- minimum connections
- maximum connections
- idle timeout
- connection timeout

---

## Read Replicas

A read replica is a copy of the primary database used for reads.

Architecture:

                  Primary DB
                      |
          -------------------------
          |                       |
          v                       v
     Read Replica 1          Read Replica 2

Writes go to:

    Primary DB

Reads can go to:

    Replicas

This improves read scalability.

---

## Read Replica Example

Write:

    Create user

goes to primary.

Read:

    View user profile

can go to replica.

This reduces pressure on the primary database.

---

## Replication Lag

Replicas are not always perfectly up to date.

Example:

User updates profile.

Primary updates immediately.

Replica updates slightly later.

During that delay, the user may see old data.

This is replication lag.

---

## Handling Replication Lag

Common strategies:

- read own writes from primary
- use replicas only for non-critical reads
- show eventual consistency
- monitor lag
- keep replication delay low

Example:

After user updates profile, read from primary for a short period.

---

## Partitioning

Partitioning splits a large table into smaller parts.

Example:

Transactions table grows huge.

Partition by month:

    transactions_2026_01
    transactions_2026_02
    transactions_2026_03

Benefits:

- faster queries
- easier maintenance
- better archival

Partitioning is often useful for time-series data.

---

## Sharding

Sharding splits data across multiple databases.

Example:

Users A-M:

    Database 1

Users N-Z:

    Database 2

Architecture:

              Application
                   |
          -------------------
          |                 |
          v                 v
       Shard 1           Shard 2

Sharding allows horizontal database scaling.

But it adds major complexity.

---

## Sharding Trade-Offs

Benefits:

- handles massive data
- increases write capacity
- distributes load

Costs:

- complex queries
- difficult joins
- harder migrations
- harder transactions
- operational complexity

Use sharding only when simpler scaling strategies are no longer enough.

---

## Multi-Tenant Databases

SaaS systems often serve many customers.

Tenancy models:

### Shared Database, Shared Tables

All tenants share tables.

Example:

    contracts
    workflows
    files

Each row has:

    workspace_id

Benefits:

- simple
- cost effective

Risks:

- tenant isolation bugs

### Shared Database, Separate Schemas

Each tenant has own schema.

Benefits:

- better isolation

Costs:

- more operational complexity

### Separate Database Per Tenant

Each tenant gets its own database.

Benefits:

- strongest isolation

Costs:

- expensive
- harder to manage

---

## Failover

Failover means switching to a backup system when the primary fails.

Example:

Primary database crashes.

Replica promoted to primary.

Architecture:

    Primary DB
        |
        v
    Replica DB

Failure:

    Replica becomes Primary

Good failover improves availability.

---

## Backup And Recovery

Scaling is useless if data cannot be recovered.

Backups protect against:

- accidental deletion
- corruption
- failed migrations
- infrastructure failure
- security incidents

Important concepts:

### RPO

Recovery Point Objective.

How much data can be lost?

Example:

    5 minutes

### RTO

Recovery Time Objective.

How long can recovery take?

Example:

    30 minutes

---

## PostgreSQL Scaling Example

Phase 1:

    Fastify API
        |
        v
    PostgreSQL

Phase 2:

Add indexes.

    Fastify API
        |
        v
    Indexed PostgreSQL

Phase 3:

Add Redis cache.

    API
     |
     v
    Redis
     |
     v
    PostgreSQL

Phase 4:

Add read replicas.

          API
           |
     --------------
     |            |
     v            v
  Primary      Replica

Phase 5:

Add partitioning for large tables.

Phase 6:

Consider sharding only if absolutely necessary.

---

## Case Study: VaultBox

VaultBox stores:

- users
- plans
- files
- storage usage
- audit logs

Potential bottlenecks:

- file metadata lookup
- storage usage calculations
- audit log growth

Possible scaling strategy:

- index user email
- index file owner id
- cache plan data
- paginate file listings
- partition audit logs by month
- use read replicas for analytics

---

## Case Study: SyncGrid

SyncGrid handles:

- providers
- API keys
- request logs
- webhook events
- teams

Potential bottlenecks:

- request log growth
- provider lookups
- API key validation
- webhook replay queries

Possible scaling strategy:

- cache provider config
- cache API key metadata
- index team_id
- index api_key prefix
- move logs to partitioned tables
- queue webhook processing

---

## Case Study: inFlowForge

inFlowForge handles:

- workflows
- executions
- triggers
- actions
- logs

Potential bottlenecks:

- execution log volume
- workflow lookup frequency
- scheduled job queries

Possible scaling strategy:

- cache workflow definitions
- index workspace_id
- index execution status
- archive old logs
- partition execution records
- use workers for execution processing

---

## Failure Scenarios

### Scenario 1: Missing Index

Query:

    SELECT *
    FROM users
    WHERE email = 'ada@example.com';

Without index:

Full table scan.

System slows down.

Fix:

    CREATE INDEX idx_users_email
    ON users(email);

---

### Scenario 2: Too Many Connections

Many API servers open too many database connections.

Database refuses new connections.

Fix:

- connection pooling
- pool limits
- PgBouncer
- reduce idle connections

---

### Scenario 3: Replica Lag

User updates profile.

Reads from replica.

Old data appears.

Fix:

- read own writes from primary
- monitor lag
- use primary for sensitive reads

---

### Scenario 4: Bad Migration

Migration locks huge table.

Application becomes unavailable.

Fix:

- test migrations
- use safe migration strategy
- migrate in phases
- avoid long locks

---

### Scenario 5: No Backups

Database corrupted.

No backup exists.

Data permanently lost.

Fix:

- automated backups
- restore testing
- backup monitoring

---

## Common Mistakes

### Mistake 1

Adding more API servers when the database is the bottleneck.

### Mistake 2

Using `SELECT *` everywhere.

### Mistake 3

No indexes on common lookup columns.

### Mistake 4

No pagination.

### Mistake 5

Ignoring connection pool limits.

### Mistake 6

Scaling with sharding too early.

### Mistake 7

No backup recovery testing.

### Mistake 8

Assuming replicas are always up to date.

---

## Design Trade-Offs

### Cache vs Database Reads

Cache improves speed.

But cache adds invalidation complexity.

### Read Replicas vs Consistency

Replicas improve read scale.

But introduce replication lag.

### Sharding vs Simplicity

Sharding improves scale.

But adds major complexity.

### Normalization vs Query Speed

Normalization reduces duplication.

Denormalization can improve read speed.

But denormalization risks inconsistency.

---

## Interview Questions

1. Why do databases become bottlenecks?
2. What is the difference between read-heavy and write-heavy workloads?
3. What is an index?
4. When should you avoid indexes?
5. What is connection pooling?
6. What is a read replica?
7. What is replication lag?
8. What is partitioning?
9. What is sharding?
10. Why is sharding difficult?
11. How would you scale PostgreSQL?
12. What are RPO and RTO?
13. How do you handle slow queries?
14. How do you design a database for multi-tenant SaaS?
15. When would you use Redis with PostgreSQL?

---

## Exercises

1. Identify likely database bottlenecks in VaultBox.
2. Identify likely database bottlenecks in SyncGrid.
3. Design indexes for a `files` table.
4. Design indexes for an `api_keys` table.
5. Explain when to use read replicas.
6. Explain why replication lag matters.
7. Design a partition strategy for audit logs.
8. Compare shared-table tenancy and database-per-tenant tenancy.
9. Explain why sharding should not be the first scaling step.
10. Draw a scaled database architecture using PostgreSQL, Redis and read replicas.

---

## Further Reading

PostgreSQL Indexes

https://www.postgresql.org/docs/current/indexes.html

PostgreSQL Performance Tips

https://www.postgresql.org/docs/current/performance-tips.html

PgBouncer

https://www.pgbouncer.org

AWS Database Scaling

https://aws.amazon.com/rds/features/read-replicas/

System Design Primer

https://github.com/donnemartin/system-design-primer

---

## Summary

Databases are often the hardest part of a system to scale because they store shared state.

Key strategies include:

- better indexing
- query optimization
- pagination
- connection pooling
- caching
- read replicas
- partitioning
- backups
- failover

Sharding exists, but it should usually be a later-stage solution.

Good database scaling starts with understanding workload, measuring bottlenecks and applying the simplest effective improvement first.

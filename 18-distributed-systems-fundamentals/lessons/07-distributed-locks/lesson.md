# Lesson 07: Distributed Locks

## Learning Objectives

By the end of this lesson you should be able to:

- Explain distributed locks.
- Understand mutual exclusion.
- Understand lock ownership.
- Understand lock expiration.
- Understand lock safety.
- Explain lock failure scenarios.
- Design systems that use distributed locks correctly.

---

## Introduction

Imagine two workers attempting to process the same task.

Worker A:

    Process Invoice #123

Worker B:

    Process Invoice #123

Both execute simultaneously.

Result:

- duplicate processing
- inconsistent state
- corrupted data

We need coordination.

One solution:

    Distributed Locks

---

## What Is A Lock?

A lock is a mechanism that grants exclusive access to a resource.

Example:

Worker A acquires lock.

Worker B waits.

Only one worker proceeds.

---

## Local Locks

Inside a single application:

Example:

    mutex.lock()

Only one thread enters critical section.

Simple.

---

## Why Local Locks Are Not Enough

Distributed systems run across multiple machines.

Example:

Node A

Node B

Node C

Local locks only affect one machine.

They cannot coordinate the cluster.

---

## Distributed Locks

Distributed locks coordinate access across multiple nodes.

Goal:

Only one node performs an operation.

Example:

Only one scheduler executes a task.

Only one worker performs cleanup.

Only one leader performs coordination.

---

## Mutual Exclusion

Core property.

At most one owner.

Example:

Lock:

    invoice_123

Owner:

    Worker A

Worker B denied.

Mutual exclusion preserved.

---

## Lock Lifecycle

Acquire

↓

Use Resource

↓

Release

Simple in theory.

Difficult in distributed systems.

---

## Example: Scheduled Jobs

Cluster:

Worker A

Worker B

Worker C

Job:

    Daily Cleanup

Without lock:

All workers execute job.

With lock:

Only one worker executes.

---

## Example: NOMMO Scheduler

Multiple schedulers running.

Task arrives.

Distributed lock ensures:

Only one scheduler assigns work.

Prevents duplicate placement.

---

## Lock Ownership

Lock should have owner.

Example:

Lock:

    backup-job

Owner:

    Worker-A

Only owner may release lock.

---

## Lock Expiration

Critical concept.

Scenario:

Worker acquires lock.

Worker crashes.

Lock never released.

System stuck forever.

Solution:

Expiration.

---

## Time-To-Live (TTL)

Example:

Lock TTL:

    30 seconds

If owner disappears:

Lock expires automatically.

Other workers can continue.

---

## Lock Renewal

Long-running tasks may renew locks.

Example:

Every 10 seconds:

    Extend lock

Prevents accidental expiration.

---

## Lock Acquisition Example

Worker A:

Acquire:

    lock:job-123

Success.

Worker B:

Acquire:

    lock:job-123

Failure.

Worker B waits.

---

## Redis Distributed Locks

Common implementation.

Command:

    SET key value NX EX 30

Meaning:

Create lock only if absent.

Expire after 30 seconds.

Simple and popular.

---

## Why Redis Works

Redis operations are atomic.

Atomic means:

All-or-nothing.

Prevents race conditions during acquisition.

---

## Lock Release Safety

Dangerous approach:

Delete lock blindly.

Problem:

Lock expired.

New owner acquired lock.

Old owner deletes lock.

Now protection disappears.

Bad outcome.

---

## Lock Tokens

Safer approach.

Lock contains unique token.

Example:

Owner:

    worker-a-token

Release only if token matches.

Protects new owners.

---

## Fencing Tokens

Advanced safety mechanism.

Example:

Worker A:

Token 5

Worker B:

Token 6

System accepts only newest token.

Protects against stale owners.

---

## Split-Brain Risks

Partition occurs.

Node A thinks lock acquired.

Node B thinks lock acquired.

Now:

Two owners exist.

Dangerous.

Distributed locking becomes difficult.

---

## Redlock

Popular Redis locking algorithm.

Uses multiple Redis nodes.

Goal:

Improve reliability.

However:

It remains controversial in distributed systems discussions.

Important to understand trade-offs.

---

## Lock Granularity

Question:

How much should a lock protect?

Fine-grained:

Many locks.

More concurrency.

More complexity.

---

Coarse-grained:

Few locks.

Simpler.

Lower concurrency.

Trade-offs exist.

---

## Lock Contention

Many workers competing.

Example:

100 workers.

1 lock.

Performance suffers.

This is contention.

---

## Avoiding Excessive Locking

Good design often reduces lock usage.

Strategies:

- partition work
- leader coordination
- idempotency
- queue ownership

Locks are useful.

Not always ideal.

---

## Idempotency Vs Locking

Sometimes idempotency is enough.

Example:

Webhook processing.

Duplicate execution tolerated.

Lock unnecessary.

Always consider alternatives.

---

## Distributed Locks In SyncGrid

Possible uses:

- webhook retries
- provider maintenance jobs
- scheduled cleanup

---

## Distributed Locks In VaultBox

Possible uses:

- quota recalculation
- storage cleanup
- metadata repair

---

## Distributed Locks In inFlowForge

Possible uses:

- workflow scheduling
- cron execution
- maintenance jobs

---

## Distributed Locks In NOMMO

Critical uses:

- scheduler ownership
- service placement
- deployment coordination
- cluster maintenance

---

## Failure Scenario 1

Worker crashes.

Lock never released.

TTL prevents permanent blockage.

---

## Failure Scenario 2

Network partition.

Multiple owners appear.

Split-brain risk.

---

## Failure Scenario 3

Lock expires too early.

Second worker acquires lock.

Duplicate execution occurs.

---

## Failure Scenario 4

High contention.

System throughput drops.

---

## Trade-Offs

### Locks

Benefits:

- coordination
- exclusivity

Costs:

- complexity
- contention
- failure handling

---

### Idempotency

Benefits:

- simpler

Costs:

- requires careful design

---

## Common Mistakes

### Mistake 1

No lock expiration.

### Mistake 2

Blind lock release.

### Mistake 3

Ignoring partitions.

### Mistake 4

Overusing locks.

### Mistake 5

Ignoring contention.

---

## Interview Questions

1. What is a distributed lock?
2. Why are local locks insufficient?
3. What is mutual exclusion?
4. Why use TTL?
5. What is lock ownership?
6. What are lock tokens?
7. What are fencing tokens?
8. What is lock contention?
9. Why can distributed locking be difficult?
10. How would NOMMO use distributed locks?
11. Why is idempotency sometimes preferable?
12. What is Redlock?

---

## Exercises

1. Design a lock for workflow scheduling.
2. Design a lock for service placement.
3. Explain lock expiration.
4. Explain fencing tokens.
5. Explain lock contention.
6. Compare locks and idempotency.
7. Draw lock acquisition flow.
8. Explain partition risks.
9. Design a Redis-based lock.
10. Explain why distributed locks are harder than local locks.

---

## Further Reading

Redis Distributed Locks

https://redis.io/docs/latest/develop/use/patterns/distributed-locks/

Martin Kleppmann On Distributed Locking

https://martin.kleppmann.com

Designing Data Intensive Applications

https://dataintensive.net

---

## Summary

Distributed locks provide exclusive access across multiple machines.

Key concepts include:

- mutual exclusion
- ownership
- TTLs
- lock tokens
- fencing tokens

They are powerful tools for coordination but require careful design to avoid failure scenarios and contention.

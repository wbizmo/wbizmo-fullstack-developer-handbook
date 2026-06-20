# Lesson 07: CAP Theorem & Consistency

## Learning Objectives

By the end of this lesson you should be able to:

- Explain CAP Theorem.
- Understand consistency.
- Understand availability.
- Understand partition tolerance.
- Understand eventual consistency.
- Analyze distributed systems trade-offs.
- Evaluate architecture decisions.

---

## Introduction

One of the most important ideas in distributed systems is:

    CAP Theorem

Many engineers hear the term but never truly understand its implications.

CAP is not just interview trivia.

It affects:

- databases
- caches
- distributed systems
- message queues
- cloud architectures

Systems such as:

- PostgreSQL clusters
- Redis clusters
- Cassandra
- DynamoDB
- Kafka

all make trade-offs related to CAP.

---

## The Core Problem

Imagine a system running on multiple servers.

Example:

        Node A
           |
           |
           |
        Node B

Normally:

Nodes communicate.

Life is good.

But networks fail.

Servers fail.

Links fail.

Packets disappear.

Distributed systems must decide what happens next.

---

## CAP Theorem Definition

CAP states:

A distributed system cannot simultaneously guarantee:

    Consistency

    Availability

    Partition Tolerance

during a network partition.

You can strongly guarantee at most two.

---

## Consistency

Consistency means:

Every node sees the same data at the same time.

Example:

User balance:

    ₦10,000

Node A:

    ₦10,000

Node B:

    ₦10,000

Both agree.

After an update:

Node A:

    ₦12,000

Node B:

    ₦12,000

Still consistent.

---

## Availability

Availability means:

Every request receives a response.

Even if part of the system is failing.

Example:

User requests profile.

System returns:

- correct data
- stale data
- partial data

But it responds.

Availability focuses on responsiveness.

---

## Partition Tolerance

A partition occurs when nodes cannot communicate.

Example:

        Node A

            X

        Node B

Network link broken.

This is a partition.

Distributed systems must continue operating somehow.

---

## Why Partition Tolerance Is Mandatory

Many people misunderstand CAP.

You cannot simply choose:

    "No Partition Tolerance"

Real networks fail.

Cloud infrastructure fails.

Regions become unavailable.

Partitions happen whether you want them or not.

In practice:

Modern distributed systems must tolerate partitions.

The real trade-off is usually:

    Consistency

vs

    Availability

during failures.

---

## CP Systems

Choose:

Consistency

+

Partition Tolerance

Sacrifice:

Availability

Example:

Node communication breaks.

System refuses some requests.

Why?

To prevent inconsistent data.

---

## CP Example

Bank transfer.

Account balance:

    ₦100,000

Network partition occurs.

System cannot verify latest balance.

Safer choice:

Reject request.

Better:

Temporary downtime

than

Incorrect money movement.

---

## AP Systems

Choose:

Availability

+

Partition Tolerance

Sacrifice:

Immediate consistency

System continues responding.

Some responses may contain stale data.

---

## AP Example

Social media likes.

User likes a post.

Server A:

    101 likes

Server B:

    100 likes

For a short time:

Different values exist.

Eventually:

All servers synchronize.

Users usually do not care.

---

## CA Systems

Theoretical:

Consistency

+

Availability

No partition tolerance.

In practice:

Rarely realistic for distributed systems.

Because partitions eventually occur.

---

## Strong Consistency

After a write:

Every read sees latest value.

Example:

Update:

    username

Immediately afterward:

Every node returns new username.

Benefits:

- simple reasoning
- correctness

Costs:

- slower
- harder to scale

---

## Eventual Consistency

Eventually all nodes converge.

Immediately after update:

Different values may exist.

Later:

Everything becomes consistent.

Benefits:

- scalable
- resilient

Costs:

- temporary inconsistency

---

## Real World Eventual Consistency

User updates profile picture.

Server A:

New image.

Server B:

Old image.

After replication:

All servers show new image.

Most users never notice.

---

## Consistency Models

### Strong Consistency

Latest value always visible.

### Eventual Consistency

Data converges eventually.

### Read-Your-Writes

User sees own updates immediately.

### Monotonic Reads

Data never moves backward.

---

## Distributed Database Example

Architecture:

         Primary
            |
      ----------------
      |              |
      v              v
  Replica A      Replica B

User updates data.

Primary updates immediately.

Replicas update later.

Question:

Should reads continue?

CAP decisions begin here.

---

## Replication Lag

Replica delay creates inconsistency.

Example:

Primary:

    status=paid

Replica:

    status=pending

This is a consistency problem.

---

## Handling Replication Lag

Options:

### Read Primary

Benefits:

- fresh data

Costs:

- higher load

### Read Replica

Benefits:

- scalable

Costs:

- stale reads

---

## CAP In Redis

Single Redis:

CAP not particularly relevant.

Redis Cluster:

Distributed system.

Trade-offs appear.

Network failures matter.

Consistency decisions matter.

---

## CAP In PostgreSQL

Primary-replica architecture:

Can favor:

- stronger consistency

or

- higher availability

depending on design.

---

## CAP In VaultBox

Storage metadata:

Usually requires strong consistency.

File analytics:

Can tolerate eventual consistency.

Different parts of the same system may use different consistency models.

---

## CAP In SyncGrid

Webhook delivery:

Eventually consistent is often acceptable.

API key validation:

Usually requires stronger consistency.

---

## CAP In inFlowForge

Workflow execution:

May tolerate eventual consistency.

Billing:

Likely requires stronger consistency.

---

## CAP In NOMMO

Control plane state:

Often requires stronger consistency.

Monitoring metrics:

Can tolerate eventual consistency.

---

## Split-Brain Problem

Dangerous failure scenario.

Node A believes:

"I am primary."

Node B believes:

"I am primary."

Now two leaders exist.

This is split-brain.

Can corrupt data.

---

## Preventing Split-Brain

Common solutions:

- leader election
- consensus algorithms
- quorum systems

Examples:

- Raft
- Paxos

---

## Quorum

Quorum means:

Majority agreement.

Example:

5 nodes.

Need:

3 confirmations

before accepting write.

Benefits:

Improves consistency.

Costs:

More coordination.

---

## Consensus Algorithms

Large distributed systems often use:

### Raft

Popular.

Easy to understand.

Used widely.

### Paxos

Powerful.

More complex.

### Zab

Used in ZooKeeper.

Consensus helps systems agree on truth.

---

## Failure Scenario 1

Network Partition

Two nodes cannot communicate.

System must choose:

Consistency

or

Availability

---

## Failure Scenario 2

Replication Lag

User sees stale data.

System remains available.

---

## Failure Scenario 3

Primary Failure

Replica promoted.

Availability maintained.

Potential consistency risks.

---

## Failure Scenario 4

Split-Brain

Multiple leaders.

Data divergence occurs.

---

## Failure Scenario 5

Region Outage

Entire data center disappears.

System architecture determines survival.

---

## Trade-Offs

### Strong Consistency

Benefits:

- correctness

Costs:

- latency
- reduced availability

---

### Eventual Consistency

Benefits:

- scalability
- resilience

Costs:

- stale reads

---

### Quorum Systems

Benefits:

- safer writes

Costs:

- slower operations

---

## Common Mistakes

### Mistake 1

Assuming distributed systems always agree instantly.

### Mistake 2

Ignoring network failures.

### Mistake 3

Treating eventual consistency as a bug.

### Mistake 4

Demanding strong consistency everywhere.

### Mistake 5

Ignoring replication lag.

### Mistake 6

Not understanding business requirements.

---

## Interview Questions

1. What is CAP Theorem?
2. What is consistency?
3. What is availability?
4. What is partition tolerance?
5. Why are partitions unavoidable?
6. What is eventual consistency?
7. What is strong consistency?
8. What is replication lag?
9. What is split-brain?
10. What is quorum?
11. What is consensus?
12. What is Raft?
13. When would you choose eventual consistency?
14. When would you choose stronger consistency?
15. How does CAP affect distributed systems?

---

## Exercises

1. Identify consistency requirements in VaultBox.
2. Identify consistency requirements in SyncGrid.
3. Identify consistency requirements in inFlowForge.
4. Compare strong and eventual consistency.
5. Draw a primary-replica architecture.
6. Explain replication lag.
7. Explain split-brain.
8. Explain quorum.
9. Explain why CAP matters.
10. Determine which data in NOMMO requires strong consistency.

---

## Further Reading

CAP Theorem Paper

https://www.cs.berkeley.edu/~brewer/cs262b-2004/PODC-keynote.pdf

Designing Data-Intensive Applications

https://dataintensive.net

Raft Consensus

https://raft.github.io

Martin Kleppmann

https://martin.kleppmann.com

System Design Primer

https://github.com/donnemartin/system-design-primer

---

## Summary

CAP Theorem is one of the foundational ideas in distributed systems.

It teaches that during network partitions, systems must balance:

- consistency
- availability

while maintaining partition tolerance.

Understanding these trade-offs is essential for designing scalable distributed architectures and making informed engineering decisions.

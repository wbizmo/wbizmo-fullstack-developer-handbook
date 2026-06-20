# Lesson 05: Consensus And Raft

## Learning Objectives

By the end of this lesson you should be able to:

- Explain consensus.
- Understand why consensus exists.
- Understand the consensus problem.
- Explain Raft at a high level.
- Understand terms, leaders and followers.
- Understand log replication.
- Understand committed entries.
- Understand why consensus is difficult.

---

## Introduction

One of the hardest problems in distributed systems is agreement.

Question:

How do multiple machines agree on truth?

Example:

Cluster:

    Node A
    Node B
    Node C

Value:

    account_balance = 100

How do all nodes agree that this is correct?

This problem is called:

    Consensus

Consensus is one of the foundations of modern distributed systems.

---

## What Is Consensus?

Consensus means:

Multiple nodes agree on the same value.

Example:

Nodes:

    A
    B
    C

All agree:

    Leader = A

or

    Version = 42

or

    Balance = 100

Consensus ensures coordinated behavior.

---

## Why Consensus Matters

Without consensus:

Different nodes may believe different things.

Example:

Node A:

    Balance = 100

Node B:

    Balance = 80

Node C:

    Balance = 120

System behavior becomes unpredictable.

---

## Real World Systems Using Consensus

Examples:

### etcd

Used by Kubernetes.

### ZooKeeper

Distributed coordination.

### Consul

Service discovery.

### CockroachDB

Distributed SQL.

### TiDB

Distributed database.

### NOMMO

Future orchestrator coordination may depend on consensus.

---

## The Consensus Problem

Distributed systems experience:

- crashes
- partitions
- latency
- lost messages

Despite these issues:

Nodes must agree.

This is difficult.

---

## Consensus Requirements

Good consensus systems provide:

### Agreement

All healthy nodes eventually agree.

### Safety

No conflicting decisions.

### Liveness

System continues making progress.

---

## Example: Leader Election

Cluster:

Node A

Node B

Node C

Question:

Who is leader?

Consensus guarantees everyone eventually agrees.

---

## Why Majority Matters

Consensus systems usually require:

Majority agreement.

Example:

5 nodes.

Need:

3 votes.

Majorities help avoid split-brain.

---

## Raft Overview

Raft is a consensus algorithm.

Created to be easier to understand than Paxos.

Raft focuses on:

- leader election
- log replication
- fault tolerance

Today it is one of the most widely used consensus algorithms.

---

## Raft Roles

Nodes can be:

### Follower

Passive.

Receives instructions.

---

### Candidate

Requests votes.

Attempts leadership.

---

### Leader

Coordinates cluster.

Handles writes.

---

## Follower State

Most nodes spend time as followers.

Responsibilities:

- receive heartbeats
- replicate logs
- vote during elections

Followers do not actively coordinate.

---

## Candidate State

Triggered when:

Heartbeat missing.

Node believes leader failed.

Candidate requests votes.

---

## Leader State

Leader responsibilities:

- receive writes
- replicate logs
- send heartbeats
- coordinate cluster

Only one leader should exist.

---

## Terms

Raft divides time into terms.

Example:

Term 1:

Leader A

Term 2:

Leader B

Term 3:

Leader C

Terms help nodes identify stale information.

---

## Election Process

Follower waits.

↓

Heartbeat missing.

↓

Become candidate.

↓

Request votes.

↓

Majority achieved.

↓

Become leader.

Simple and effective.

---

## Heartbeats

Leaders periodically send:

    I am leader

Followers reset election timers.

As long as heartbeats continue:

No election occurs.

---

## Log Replication

One of Raft's most important responsibilities.

Leader receives write.

Example:

    Create User

Leader writes entry.

Then replicates to followers.

---

## Log Example

Leader:

    Entry 1
    Entry 2
    Entry 3

Followers replicate same entries.

Goal:

Identical logs.

---

## Commit Process

Leader receives command.

↓

Write log entry.

↓

Replicate to majority.

↓

Mark committed.

↓

Apply change.

Consensus achieved.

---

## Why Majority Replication Matters

Example:

5 nodes.

Write replicated to:

3 nodes.

Majority achieved.

Entry committed.

Even if one node later fails:

Data survives.

---

## Committed Entries

Committed entries are considered durable.

They will survive leader changes.

This is critical.

---

## Leader Failure

Leader crashes.

Example:

Leader A fails.

Followers stop receiving heartbeats.

Election begins.

New leader elected.

Cluster continues operating.

---

## Log Consistency

Raft ensures:

Followers eventually match leader.

This prevents conflicting histories.

---

## Split-Brain Prevention

Majority voting helps prevent:

Multiple leaders.

Only one node can obtain majority.

This greatly reduces split-brain risk.

---

## Why Consensus Is Expensive

Consensus requires:

- communication
- voting
- replication

These operations increase latency.

Consensus improves correctness.

At a performance cost.

---

## Raft In Kubernetes

Kubernetes uses etcd.

etcd uses Raft.

Cluster state remains consistent through consensus.

---

## Raft In NOMMO

Potential future architecture:

Workers

↓

Leader

↓

Consensus Cluster

Consensus could protect:

- scheduling decisions
- service placement
- cluster state

---

## Consensus In Databases

Distributed databases often use consensus.

Examples:

- CockroachDB
- TiDB
- YugabyteDB

Consensus protects correctness.

---

## Consensus Vs Availability

Consensus improves correctness.

But can reduce availability during severe failures.

Trade-offs always exist.

---

## Paxos

Another consensus algorithm.

Historically important.

Powerful.

Harder to understand.

Raft became popular because it is easier to teach and implement.

---

## Failure Scenario 1

Leader crash.

Election begins.

New leader elected.

---

## Failure Scenario 2

Network partition.

Majority side continues.

Minority side cannot elect leader.

---

## Failure Scenario 3

Follower crash.

Cluster remains healthy.

Majority preserved.

---

## Failure Scenario 4

Message delay.

Election may occur unexpectedly.

Timeout tuning matters.

---

## Failure Scenario 5

Node rejoins cluster.

Missing log entries replicated.

State restored.

---

## Trade-Offs

### Consensus

Benefits:

- correctness
- coordination
- safety

Costs:

- complexity
- latency
- operational overhead

---

### Majority Voting

Benefits:

- prevents conflicting leaders

Costs:

- requires quorum

---

## Common Mistakes

### Mistake 1

Assuming consensus is free.

### Mistake 2

Ignoring quorum requirements.

### Mistake 3

Ignoring partitions.

### Mistake 4

Ignoring log replication.

### Mistake 5

Treating consensus as a database feature only.

---

## Interview Questions

1. What is consensus?
2. Why is consensus needed?
3. What is Raft?
4. What are Raft roles?
5. What is a follower?
6. What is a candidate?
7. What is a leader?
8. What is a term?
9. What is log replication?
10. What is a committed entry?
11. Why is majority voting important?
12. How does Raft elect leaders?
13. What happens if a leader crashes?
14. Why is consensus difficult?
15. Why does Kubernetes depend on consensus?

---

## Exercises

1. Draw a Raft cluster.
2. Simulate a leader election.
3. Simulate log replication.
4. Explain majority voting.
5. Explain committed entries.
6. Explain quorum.
7. Explain why consensus improves correctness.
8. Explain how NOMMO could use consensus.
9. Compare Raft and simple leader election.
10. Explain why consensus introduces latency.

---

## Further Reading

Raft Official Site

https://raft.github.io

Raft Paper

https://raft.github.io/raft.pdf

etcd

https://etcd.io

Designing Data Intensive Applications

https://dataintensive.net

---

## Summary

Consensus allows distributed systems to agree on truth despite failures.

Raft achieves this through:

- leader election
- majority voting
- log replication
- committed entries

Consensus is one of the most important foundations of distributed databases, orchestration systems and cloud platforms.

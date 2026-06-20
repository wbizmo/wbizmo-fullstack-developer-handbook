# Lesson 03: Time, Clocks And Ordering

## Learning Objectives

By the end of this lesson you should be able to:

- Understand why time is difficult in distributed systems.
- Understand physical clocks.
- Understand logical clocks.
- Understand event ordering.
- Explain clock drift.
- Explain causality.
- Understand Lamport clocks at a beginner level.

---

## Introduction

On a single machine, time seems simple.

Example:

Event A:

    10:00:01

Event B:

    10:00:02

Clearly:

    A happened before B

In distributed systems, things become much more complicated.

Different machines have different clocks.

Networks introduce delays.

Messages arrive late.

Events may appear out of order.

One of the hardest questions becomes:

    What happened first?

---

## Time On A Single Machine

Single process:

Event A

↓

Event B

↓

Event C

Order is obvious.

The CPU executes instructions sequentially.

---

## Time Across Multiple Machines

Consider:

Node A

Node B

Both have clocks.

Question:

Are the clocks identical?

Almost never.

---

## Clock Drift

Clocks slowly diverge.

Example:

Node A:

    10:00:00

Node B:

    09:59:58

Difference:

    2 seconds

This is clock drift.

---

## Why Clock Drift Happens

Causes:

- hardware differences
- operating systems
- clock inaccuracies
- synchronization delays

All machines drift over time.

---

## NTP

Most systems use:

Network Time Protocol (NTP)

Purpose:

Synchronize clocks.

Architecture:

Machine

↓

NTP Server

↓

Reference Clock

NTP reduces drift.

It does not eliminate it.

---

## The Ordering Problem

Example:

Node A:

    UserCreated

Node B:

    EmailSent

Question:

Which happened first?

Timestamps alone may not be trustworthy.

---

## Message Delays

Example:

Node A sends message.

Network delay:

    500ms

Node B receives later.

Timestamp order may appear incorrect.

---

## Simultaneous Events

Node A:

    10:00:00

Node B:

    10:00:00

Both create events.

Question:

Which happened first?

Sometimes there is no meaningful answer.

---

## Physical Clocks

Physical clocks represent actual time.

Examples:

- wall clock time
- UTC
- timestamps

Advantages:

- human readable

Problems:

- drift
- synchronization errors

---

## Logical Clocks

Logical clocks focus on ordering.

Not actual time.

Goal:

Determine relationships between events.

---

## Causality

Critical concept.

Example:

Event A causes Event B.

User registers.

↓

Welcome email sent.

Clearly:

Registration happened before email.

This relationship is causality.

---

## Happens-Before Relationship

Introduced by Leslie Lamport.

If:

Event A causes Event B

Then:

A happened before B.

This is more useful than clock time.

---

## Lamport Clocks

Lamport created logical clocks.

Goal:

Track event ordering.

Each node maintains counter.

Example:

Node A:

    1
    2
    3

Node B:

    1
    2
    3

Messages carry counter values.

Ordering becomes possible.

---

## Lamport Clock Rules

Rule 1:

Increment clock before event.

Rule 2:

Send clock value with messages.

Rule 3:

Receiver updates:

    max(local, received) + 1

Simple.

Powerful.

---

## Example

Node A:

Clock = 5

Message sent.

Node B:

Clock = 3

Receives:

5

New value:

    max(3,5)+1

Result:

    6

Ordering preserved.

---

## What Lamport Clocks Solve

They help answer:

Could event A have influenced event B?

Useful for distributed coordination.

---

## What Lamport Clocks Do Not Solve

They do not provide actual timestamps.

Example:

Clock:

    500

Does not mean:

    5:00 PM

Logical clocks track order, not real time.

---

## Vector Clocks

Extension of Lamport clocks.

Track causality more accurately.

Example:

Node A:

    [3,0]

Node B:

    [3,5]

Can determine relationships more precisely.

---

## Why Ordering Matters

Many systems depend on order.

Examples:

- payments
- deployments
- workflow execution
- distributed databases

Incorrect ordering can create bugs.

---

## SyncGrid Example

Events:

ChargeCreated

↓

WebhookDelivered

Correct order required.

---

## VaultBox Example

Events:

FileUploaded

↓

MetadataExtracted

↓

ThumbnailGenerated

Order matters.

---

## inFlowForge Example

Events:

WorkflowCreated

↓

WorkflowTriggered

↓

WorkflowExecuted

Order must be maintained.

---

## NOMMO Example

Events:

WorkerJoined

↓

TaskAssigned

↓

TaskCompleted

Incorrect ordering causes orchestration issues.

---

## Event Ordering Strategies

Common approaches:

- timestamps
- logical clocks
- sequence numbers
- leader coordination

Each has trade-offs.

---

## Distributed Logs

Systems like Kafka maintain ordered logs.

Example:

Event 1

Event 2

Event 3

Consumers process sequentially.

Ordering becomes easier.

---

## Time-Based Bugs

Examples:

- duplicate processing
- stale writes
- inconsistent state
- race conditions

Often caused by ordering assumptions.

---

## Race Conditions

Two events compete.

Example:

Update Balance

↓

Withdraw Money

Order changes outcome.

Distributed systems must handle this carefully.

---

## Clock Synchronization Limits

Perfect synchronization is impossible.

Networks introduce uncertainty.

Machines drift.

Latency varies.

Engineers design around this reality.

---

## Failure Scenario 1

Clock drift.

Nodes disagree on timestamps.

---

## Failure Scenario 2

Delayed message.

Event arrives late.

Ordering appears wrong.

---

## Failure Scenario 3

Race condition.

Conflicting updates occur.

---

## Failure Scenario 4

Workflow events processed out of order.

System state becomes inconsistent.

---

## Common Mistakes

### Mistake 1

Trusting timestamps completely.

### Mistake 2

Ignoring clock drift.

### Mistake 3

Ignoring causality.

### Mistake 4

Assuming message order.

### Mistake 5

Assuming simultaneous events are easy to reason about.

---

## Interview Questions

1. Why is time difficult in distributed systems?
2. What is clock drift?
3. What is NTP?
4. What is causality?
5. What is a logical clock?
6. What is a Lamport clock?
7. What problem does Lamport solve?
8. What is a vector clock?
9. Why does ordering matter?
10. Why can't clocks be perfectly synchronized?
11. What is a race condition?
12. How would you preserve event ordering?

---

## Exercises

1. Explain clock drift.
2. Explain causality.
3. Simulate Lamport clocks for two nodes.
4. Draw event ordering for SyncGrid.
5. Draw event ordering for VaultBox.
6. Draw event ordering for NOMMO.
7. Explain why timestamps can be misleading.
8. Compare physical and logical clocks.
9. Explain race conditions.
10. Explain why ordering becomes difficult at scale.

---

## Further Reading

Time, Clocks and the Ordering of Events

https://lamport.azurewebsites.net/pubs/time-clocks.pdf

Designing Data Intensive Applications

https://dataintensive.net

Distributed Systems For Fun And Profit

https://book.mixu.net/distsys/

---

## Summary

Time becomes surprisingly complicated in distributed systems.

Because machines have independent clocks, engineers often rely on:

- causality
- logical clocks
- ordering protocols

rather than trusting timestamps alone.

Understanding time and ordering is essential for building reliable distributed systems.

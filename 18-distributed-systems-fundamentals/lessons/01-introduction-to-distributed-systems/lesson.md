# Lesson 01: Introduction To Distributed Systems

## Learning Objectives

By the end of this lesson you should be able to:

- Define distributed systems.
- Explain why distributed systems exist.
- Understand nodes and communication.
- Understand scalability motivations.
- Understand distributed system challenges.
- Recognize distributed systems in real-world software.

---

## Introduction

Many applications begin on a single machine.

Example:

    Fastify API
        |
        v
    PostgreSQL

Everything runs together.

Simple.

Easy to understand.

Easy to operate.

This is called a monolithic deployment.

As traffic grows, however, a single machine eventually becomes insufficient.

Engineers then split responsibilities across multiple machines.

This is the beginning of distributed systems.

---

## What Is A Distributed System?

A distributed system is:

A collection of independent computers that work together and appear as a single system to users.

Users do not care:

- which server responded
- where data is stored
- which node processed work

Users simply expect the service to work.

---

## Simple Example

Single machine:

    Users
      |
      v
     API
      |
      v
 Database

Distributed version:

           Users
              |
              v
       Load Balancer
              |
      ----------------
      |      |       |
      v      v       v
    API1   API2    API3
              |
              v
          PostgreSQL

Multiple machines now participate.

---

## Why Distributed Systems Exist

The primary reasons are:

### Scalability

More users.

More requests.

More data.

More jobs.

---

### Availability

One server fails.

System continues operating.

---

### Reliability

Failures become survivable.

---

### Performance

Workload can be distributed.

---

### Geographic Distribution

Users worldwide can be served more efficiently.

---

## Real World Examples

Most systems you use daily are distributed.

Examples:

### Google Search

Thousands of servers.

### Netflix

Thousands of services.

### YouTube

Massive distributed storage.

### WhatsApp

Distributed messaging infrastructure.

### GitHub

Distributed backend architecture.

---

## Distributed Systems In Your Portfolio

You have already encountered distributed systems concepts.

### SyncGrid

Components:

- API
- Redis
- PostgreSQL
- workers
- webhook processing

---

### VaultBox

Components:

- API
- storage layer
- Redis
- PostgreSQL

---

### inFlowForge

Components:

- API
- queue
- workers
- database

---

### Argus

Components:

- monitoring agents
- central API
- alerts
- dashboards

---

### NOMMO

Components:

- workers
- orchestrator
- scheduler
- heartbeat system
- service registry

NOMMO is fundamentally a distributed systems project.

---

## Nodes

A node is an individual machine participating in the system.

Example:

Node A

Node B

Node C

Each node may perform a different role.

---

## Node Roles

Examples:

### API Node

Handles requests.

---

### Database Node

Stores data.

---

### Worker Node

Processes jobs.

---

### Cache Node

Stores temporary data.

---

## Communication

Distributed systems communicate through networks.

Examples:

HTTP

HTTPS

gRPC

TCP

Message Queues

Events

---

## Distributed System Architecture

Example:

          Client
             |
             v
            API
             |
     ----------------
     |              |
     v              v
   Redis      PostgreSQL

Even this simple architecture is distributed.

Multiple independent components communicate over a network.

---

## The Illusion Of One System

Users see:

    vaultbox.com

Internally:

- API servers
- databases
- caches
- queues
- workers

Many systems.

One experience.

Distributed systems create that illusion.

---

## The Hard Part

Single-machine software is difficult.

Distributed software is much harder.

Why?

Because networks are unreliable.

Machines fail.

Messages are delayed.

Clocks differ.

Nodes disagree.

These problems do not exist inside a single process.

---

## Fallacies Of Distributed Computing

Engineers often incorrectly assume:

- network is reliable
- latency is zero
- bandwidth is infinite
- network is secure
- topology never changes
- transport cost is zero

All are false.

---

## Example: Network Failure

Node A

↓

Send Message

↓

Node B

What happens if:

- cable unplugged?
- cloud issue?
- packet loss?
- timeout?

Distributed systems must handle failure.

---

## Example: Slow Network

Node A

expects response:

    20ms

Actual response:

    5 seconds

Questions:

- Is node down?
- Is network slow?
- Should request retry?

Distributed systems face ambiguity constantly.

---

## Partial Failure

One of the most important concepts.

Single machine:

Entire system fails.

Distributed system:

Part of system fails.

Others continue running.

Example:

Redis unavailable.

API still works.

Database still works.

This is partial failure.

---

## Why Partial Failure Is Difficult

Example:

API can reach database.

Worker cannot reach database.

Question:

Is database healthy?

Depends on perspective.

Distributed systems often contain incomplete information.

---

## Scaling Through Distribution

Example:

One worker:

    100 jobs/minute

Ten workers:

    1000 jobs/minute

Work distributed.

Capacity increases.

---

## Reliability Through Distribution

Single API:

Failure

↓

Outage

Multiple APIs:

Failure

↓

Traffic rerouted

↓

System survives

---

## Trade-Offs

Benefits:

- scalability
- reliability
- availability

Costs:

- complexity
- coordination
- debugging difficulty

Distributed systems trade simplicity for scale.

---

## Failure Scenario 1

Worker crashes.

Other workers continue.

---

## Failure Scenario 2

Database unavailable.

Application degraded.

---

## Failure Scenario 3

Network partition.

Nodes cannot communicate.

System behavior becomes uncertain.

---

## Failure Scenario 4

Message lost.

Consumer never receives event.

System must detect and recover.

---

## Common Mistakes

### Mistake 1

Assuming network is reliable.

### Mistake 2

Ignoring partial failures.

### Mistake 3

Ignoring retries.

### Mistake 4

Ignoring observability.

### Mistake 5

Treating distributed systems like single-machine systems.

---

## Interview Questions

1. What is a distributed system?
2. Why do distributed systems exist?
3. What is a node?
4. What is partial failure?
5. Why are distributed systems difficult?
6. What are the benefits of distribution?
7. What are the drawbacks?
8. What assumptions are dangerous?
9. Why does NOMMO qualify as a distributed system?
10. Why does inFlowForge contain distributed system concepts?

---

## Exercises

1. Draw the architecture of SyncGrid.
2. Draw the architecture of VaultBox.
3. Draw the architecture of inFlowForge.
4. Identify distributed components in NOMMO.
5. Explain partial failure.
6. Explain why networks introduce complexity.
7. Identify nodes in your projects.
8. List three benefits of distributed systems.
9. List three risks of distributed systems.
10. Explain why observability becomes more important as systems grow.

---

## Further Reading

Designing Data Intensive Applications

https://dataintensive.net

Martin Kleppmann

https://martin.kleppmann.com

Distributed Systems For Fun And Profit

https://book.mixu.net/distsys/

---

## Summary

Distributed systems are collections of independent machines working together as a unified service.

They exist because they provide:

- scalability
- reliability
- availability
- performance

However, they introduce new challenges:

- network failures
- partial failures
- coordination
- consistency
- observability

The remainder of this module explores how engineers manage those challenges.

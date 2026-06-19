# Lesson 01: What Is System Design?

## Learning Objectives

By the end of this lesson you should be able to:

- Explain system design.
- Distinguish between software development and system design.
- Understand functional requirements.
- Understand non-functional requirements.
- Understand scalability, reliability and availability.
- Understand engineering trade-offs.
- Understand why architecture matters.

---

## Introduction

Most developers learn how to write code.

Fewer learn how to design systems.

System Design is the process of planning how software components interact to satisfy business requirements while remaining scalable, reliable, secure and maintainable.

Writing a function is programming.

Designing how thousands or millions of users interact with an application is system design.

For example:

A login endpoint:

    POST /login

is software development.

Designing:

- authentication service
- database
- cache
- session storage
- rate limiting
- monitoring

is system design.

---

## What Problems Does System Design Solve?

As systems grow:

- users increase
- traffic increases
- storage grows
- complexity grows

Questions appear:

- Can the system handle 10 users?
- Can it handle 10,000 users?
- Can it handle 10 million users?

System design answers those questions.

---

## Functional Requirements

Functional requirements describe:

    What the system does.

Example:

VaultBox API

Functional requirements:

- upload files
- download files
- authenticate users
- generate signed URLs

SyncGrid API

Functional requirements:

- create API keys
- process requests
- route providers
- receive webhooks

---

## Non-Functional Requirements

Non-functional requirements describe:

    How well the system performs.

Examples:

- scalability
- reliability
- availability
- latency
- security
- maintainability

Many engineers fail because they focus only on functionality.

A system that works but crashes under load is still a bad system.

---

## Scalability

Scalability is the ability of a system to handle growth.

Example:

Today:

    100 users

Tomorrow:

    100,000 users

Can the system still function?

If yes:

It scales.

---

## Reliability

Reliability means:

The system behaves correctly.

Example:

Money transfers should not randomly disappear.

Authentication should not randomly fail.

Data should not become corrupted.

---

## Availability

Availability means:

The system is accessible when users need it.

Example:

99% availability

≈ 3.65 days downtime per year

99.9% availability

≈ 8.7 hours downtime per year

99.99% availability

≈ 52 minutes downtime per year

---

## Maintainability

Maintainability means:

Engineers can modify the system safely.

Bad systems:

- difficult to understand
- difficult to debug
- difficult to extend

Good systems:

- modular
- documented
- predictable

---

## Performance

Performance measures:

How quickly the system responds.

Examples:

Response Time:

    50ms

    500ms

    5s

Users notice poor performance quickly.

---

## Architecture Diagram

Simple API:

                Users
                  |
                  v
              Load Balancer
                  |
                  v
               API Layer
                  |
                  v
             PostgreSQL

As traffic grows:

                Users
                  |
                  v
              Load Balancer
                  |
        ---------------------
        |         |         |
        v         v         v
      API1      API2      API3
        |
        v
       Redis
        |
        v
    PostgreSQL

Architecture evolves with scale.

---

## Trade-Offs

There are no perfect systems.

Every decision has costs.

Example:

Cache everything

Benefits:

- speed

Costs:

- complexity
- stale data

Example:

Replicate database

Benefits:

- scale

Costs:

- synchronization complexity

Engineering is often choosing the least harmful trade-off.

---

## Failure Scenarios

Ask:

What happens if:

- database fails?
- Redis fails?
- worker crashes?
- network becomes slow?
- server restarts?

Good system design anticipates failure.

Bad system design assumes failure never happens.

---

## Real World Example

Consider inFlowForge.

Functional Requirements:

- create workflows
- execute workflows
- schedule workflows

Non-Functional Requirements:

- reliable execution
- scalable processing
- fast API responses

Architecture may include:

- Fastify API
- PostgreSQL
- Redis
- BullMQ workers

This is already a system design discussion.

---

## Common Mistakes

### Mistake 1

Thinking system design means drawing boxes.

It does not.

System design means making engineering decisions.

### Mistake 2

Ignoring non-functional requirements.

### Mistake 3

Designing only for current traffic.

### Mistake 4

Premature over-engineering.

### Mistake 5

Assuming systems never fail.

---

## Interview Questions

1. What is system design?
2. What is scalability?
3. What is reliability?
4. What is availability?
5. What is maintainability?
6. Difference between functional and non-functional requirements?
7. Why are trade-offs unavoidable?
8. Why must engineers plan for failure?

---

## Exercises

1. Identify functional requirements for VaultBox.
2. Identify non-functional requirements for VaultBox.
3. Identify functional requirements for SyncGrid.
4. Identify non-functional requirements for SyncGrid.
5. Draw a simple architecture for Cashflowr.
6. Explain three possible failure scenarios.

---

## Further Reading

System Design Primer

https://github.com/donnemartin/system-design-primer

Google Site Reliability Engineering

https://sre.google

Martin Fowler Architecture Articles

https://martinfowler.com

---

## Summary

System Design is the discipline of designing software systems that are scalable, reliable, maintainable and efficient.

Programming builds components.

System Design determines how those components work together.

The rest of this module focuses on the principles used to design production systems.

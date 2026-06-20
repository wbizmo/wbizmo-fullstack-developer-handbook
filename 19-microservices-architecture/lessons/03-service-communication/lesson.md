# Lesson 03: Service Communication

## Learning Objectives

By the end of this lesson you should be able to:

- Explain service communication.
- Compare synchronous and asynchronous communication.
- Understand REST communication.
- Understand gRPC communication.
- Understand messaging systems.
- Design service interaction patterns.
- Avoid common communication pitfalls.

---

## Introduction

Microservices are independent.

However:

They rarely operate alone.

Services must communicate.

Example:

SyncGrid

Auth Service

↓

Billing Service

↓

Provider Service

↓

Webhook Service

Communication becomes critical.

---

## Why Service Communication Matters

Without communication:

Services cannot cooperate.

Examples:

- authentication
- payments
- notifications
- workflows
- deployments

Modern systems depend heavily on service interaction.

---

## Communication Categories

Two major categories:

### Synchronous

Request

↓

Immediate response

---

### Asynchronous

Request

↓

Queue/Event

↓

Later processing

---

## Synchronous Communication

Examples:

- REST
- HTTP
- HTTPS
- gRPC

Caller waits for response.

---

## Example

Auth Service

↓

Validate User

↓

Response

Request completes immediately.

---

## Advantages

Benefits:

- simple reasoning
- immediate results
- straightforward debugging

---

## Drawbacks

Problems:

- dependency latency
- cascading failures
- tight runtime coupling

---

## Request Chain Example

User Request

↓

API Gateway

↓

Auth Service

↓

Billing Service

↓

Provider Service

↓

Database

Latency accumulates.

---

## Cascading Failure Example

Provider Service fails.

↓

Billing waits.

↓

Auth waits.

↓

Gateway waits.

↓

Users suffer.

One failure impacts many services.

---

## REST Communication

Most common approach.

Example:

    GET /users/123

    POST /payments

Simple.

Widely supported.

---

## REST Advantages

Benefits:

- easy to learn
- language agnostic
- excellent tooling

---

## REST Drawbacks

Problems:

- larger payloads
- text serialization
- higher latency than binary protocols

---

## gRPC

Modern service communication framework.

Built on:

HTTP/2

Uses:

Protocol Buffers

Binary format.

---

## gRPC Advantages

Benefits:

- faster
- smaller payloads
- strongly typed contracts

Common inside large organizations.

---

## gRPC Drawbacks

Problems:

- steeper learning curve
- less browser friendly

---

## Internal vs External APIs

Common architecture:

External:

REST

Internal:

gRPC

Best of both worlds.

---

## Asynchronous Communication

Services communicate through messages.

Examples:

- queues
- events
- streams

Caller does not wait.

---

## Example

Order Service

↓

Event Published

↓

Notification Service

↓

Email Sent

Services decoupled.

---

## Messaging Systems

Examples:

- RabbitMQ
- Kafka
- NATS
- Redis Streams
- SQS

Enable asynchronous communication.

---

## Event Driven Communication

Event occurs.

↓

Published

↓

Consumers react

Example:

UserRegistered

↓

Email Service reacts

↓

Analytics Service reacts

↓

Audit Service reacts

Powerful pattern.

---

## Point-To-Point Messaging

Producer

↓

Queue

↓

Consumer

Single consumer processes message.

---

## Publish-Subscribe

Producer

↓

Topic

↓

Many consumers

Multiple systems react independently.

---

## Communication Patterns

### Request-Response

Immediate response expected.

---

### Fire-And-Forget

Send message.

Move on.

---

### Event Driven

Publish event.

Consumers react.

---

### Streaming

Continuous data flow.

---

## Communication In SyncGrid

Examples:

Auth

↓

Provider Routing

↓

Webhook Delivery

Mix of synchronous and asynchronous communication.

---

## Communication In VaultBox

Upload

↓

Storage

↓

Thumbnail Generation

↓

Virus Scan

Events useful here.

---

## Communication In inFlowForge

Workflow Trigger

↓

Queue

↓

Worker

↓

Action Execution

Asynchronous processing dominates.

---

## Communication In NOMMO

Scheduler

↓

Workers

↓

Health Reports

↓

Registry

Mix of:

- RPC
- events
- heartbeats

---

## API Contracts

Services require clear contracts.

Example:

Request:

    user_id

Response:

    profile

Contract stability matters.

---

## Versioning

Services evolve.

Example:

    /v1/users

    /v2/users

Versioning prevents breakage.

---

## Communication Failures

Possible issues:

- timeout
- retry storm
- network partition
- service unavailable

Communication design must anticipate failure.

---

## Retry Strategy

Transient failures occur.

Use:

- retries
- exponential backoff
- idempotency

Avoid aggressive retries.

---

## Timeouts

Never wait forever.

Example:

Request timeout:

    3 seconds

Failure handled gracefully.

---

## Circuit Breakers

Dependency unhealthy.

↓

Circuit opens.

↓

Fail fast.

Protects system.

---

## Bulkheads

Separate communication paths.

Failure in one area should not impact everything.

---

## Trade-Offs

### Synchronous

Benefits:

- simplicity

Costs:

- coupling
- latency

---

### Asynchronous

Benefits:

- scalability
- resilience

Costs:

- complexity
- eventual consistency

---

## Common Mistakes

### Mistake 1

Everything synchronous.

### Mistake 2

Everything asynchronous.

### Mistake 3

No retries.

### Mistake 4

No timeouts.

### Mistake 5

No idempotency.

---

## Interview Questions

1. What is synchronous communication?
2. What is asynchronous communication?
3. What is REST?
4. What is gRPC?
5. What is event-driven communication?
6. What is publish-subscribe?
7. What is request-response?
8. Why use queues?
9. Why use events?
10. Why are timeouts important?
11. What is a circuit breaker?
12. How would SyncGrid communicate internally?
13. How would NOMMO communicate internally?
14. Why are contracts important?
15. Why does communication complexity grow with services?

---

## Exercises

1. Draw a request-response architecture.
2. Draw a publish-subscribe architecture.
3. Design SyncGrid communication flows.
4. Design VaultBox communication flows.
5. Design NOMMO communication flows.
6. Compare REST and gRPC.
7. Compare synchronous and asynchronous communication.
8. Explain circuit breakers.
9. Explain retry storms.
10. Explain why communication failures are inevitable.

---

## Further Reading

gRPC

https://grpc.io

RabbitMQ

https://rabbitmq.com

Apache Kafka

https://kafka.apache.org

Microservices.io

https://microservices.io

---

## Summary

Service communication is the foundation of microservice architectures.

Engineers must balance:

- synchronous communication
- asynchronous communication
- latency
- resilience
- simplicity
- scalability

Choosing the right communication model is one of the most important architectural decisions in distributed systems.

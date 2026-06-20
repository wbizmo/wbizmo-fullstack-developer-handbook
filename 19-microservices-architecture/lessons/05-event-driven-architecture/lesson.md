# Lesson 05: Event Driven Architecture

## Learning Objectives

- Understand events.
- Understand event-driven systems.
- Understand producers and consumers.
- Understand loose coupling.
- Understand event processing.

---

## Introduction

Traditional systems use:

Request

↓

Response

Event-driven systems work differently.

Something happens.

↓

Event emitted.

↓

Interested systems react.

---

## What Is An Event?

An event represents something that happened.

Examples:

UserRegistered

PaymentSucceeded

FileUploaded

WorkflowCompleted

---

## Producer

Creates event.

Example:

Auth Service

↓

UserRegistered

---

## Consumer

Reacts to event.

Example:

Email Service

↓

Send Welcome Email

---

## Event Flow

Producer

↓

Message Broker

↓

Consumer

---

## Benefits

- loose coupling
- scalability
- resilience
- flexibility

---

## Drawbacks

- debugging complexity
- eventual consistency
- operational overhead

---

## SyncGrid Example

ChargeCreated

↓

Webhook Processor

↓

Audit Service

↓

Analytics Service

---

## VaultBox Example

FileUploaded

↓

Virus Scanner

↓

Thumbnail Generator

↓

Analytics

---

## inFlowForge Example

TriggerActivated

↓

Execution Worker

↓

Notification Service

---

## NOMMO Example

WorkerJoined

↓

Registry Updated

↓

Scheduler Updated

↓

Monitoring Updated

---

## Event Brokers

Examples:

- Kafka
- RabbitMQ
- NATS
- Redis Streams

---

## Eventual Consistency

Events propagate over time.

State eventually converges.

Immediate consistency not guaranteed.

---

## Common Mistakes

- missing idempotency
- poor event naming
- oversized events
- no monitoring

---

## Summary

Event-driven architecture enables loosely coupled and highly scalable microservice systems.

# Lesson 04: Distributed Tracing

## Learning Objectives

By the end of this lesson you should be able to:

- Explain distributed tracing.
- Understand spans and traces.
- Follow request journeys.
- Troubleshoot distributed systems.
- Design trace-enabled architectures.

---

## Introduction

Modern systems are distributed.

A single request may touch:

- API
- Redis
- PostgreSQL
- Queue
- Workers
- External APIs

Finding bottlenecks becomes difficult.

Tracing solves this.

---

## What Is A Trace?

A trace represents the journey of a request.

Example:

Client

↓

API

↓

Redis

↓

PostgreSQL

↓

Response

Entire path recorded.

---

## What Is A Span?

A span represents a single operation.

Example:

Trace:

    Request 123

Contains spans:

- API span
- Redis span
- Database span

---

## Trace Hierarchy

Trace

↓

Span

↓

Sub-span

This structure allows detailed visibility.

---

## Example Trace

Request:

    Create Workflow

Trace:

API:
    50ms

Redis:
    10ms

PostgreSQL:
    250ms

Queue:
    5ms

Problem identified:

Database latency.

---

## Why Tracing Matters

Logs:

Tell you events.

Metrics:

Tell you health.

Traces:

Show request flow.

All three are necessary.

---

## Distributed Systems Problem

Without tracing:

Request fails.

Question:

Where?

API?

Redis?

Database?

Queue?

Provider?

Unknown.

---

## With Tracing

Request ID:

    trace_abc

Visible across:

- API
- Redis
- Database
- Workers

Root cause becomes easier to identify.

---

## OpenTelemetry

Most popular observability standard.

Supports:

- traces
- metrics
- logs

Widely adopted.

---

## Trace Context Propagation

Request enters:

API

↓

Worker

↓

External Service

Trace ID travels with request.

All operations remain connected.

---

## SyncGrid Example

Request:

Create charge

↓

Provider

↓

Webhook

↓

Retry Worker

Tracing reveals full lifecycle.

---

## VaultBox Example

Upload

↓

Storage

↓

Database

↓

Virus Scan

↓

Thumbnail Generation

Tracing reveals slow components.

---

## NOMMO Example

Deployment

↓

Scheduler

↓

Worker

↓

Router

↓

Health Checks

Tracing provides operational visibility.

---

## Common Mistakes

### Mistake 1

No trace IDs.

### Mistake 2

Partial tracing.

### Mistake 3

Ignoring workers.

### Mistake 4

Ignoring external APIs.

---

## Failure Scenarios

### Scenario 1

Slow database.

Tracing identifies latency source.

---

### Scenario 2

Queue delays.

Tracing reveals bottleneck.

---

### Scenario 3

Provider latency.

Tracing shows external dependency issue.

---

## Interview Questions

1. What is distributed tracing?
2. What is a trace?
3. What is a span?
4. Why use tracing?
5. What is context propagation?
6. What is OpenTelemetry?

---

## Exercises

1. Draw a trace for SyncGrid.
2. Draw a trace for VaultBox.
3. Draw a trace for NOMMO.
4. Explain span hierarchy.
5. Explain context propagation.

---

## Further Reading

OpenTelemetry

https://opentelemetry.io

Jaeger

https://www.jaegertracing.io

Grafana Tempo

https://grafana.com/oss/tempo/

---

## Summary

Distributed tracing provides visibility into request journeys across systems.

It is often the fastest way to locate bottlenecks in complex architectures.

# Lesson 01: Introduction To Observability

## Learning Objectives

By the end of this lesson you should be able to:

- Define observability.
- Distinguish monitoring from observability.
- Understand production visibility.
- Understand telemetry.
- Explain why observability matters.
- Understand the pillars of observability.

---

## Introduction

Imagine your API suddenly becomes slow.

Users complain.

Requests begin failing.

Question:

Why?

Without observability:

You are guessing.

With observability:

You investigate.

Observability helps engineers understand what is happening inside systems.

---

## What Is Observability?

Observability is the ability to understand the internal state of a system from its external outputs.

Outputs include:

- logs
- metrics
- traces
- events

Observability helps answer:

What happened?

Why did it happen?

Where did it happen?

---

## Monitoring vs Observability

Monitoring asks:

Is something wrong?

Observability asks:

Why is it wrong?

Example:

Monitoring:

    CPU = 95%

Observability:

    Which request caused it?

Monitoring detects problems.

Observability explains problems.

---

## Why Observability Matters

Production systems fail.

Examples:

- slow databases
- failing APIs
- memory leaks
- queue backlogs
- network failures

Without observability:

Troubleshooting becomes difficult.

---

## Telemetry

Telemetry is operational data emitted by systems.

Examples:

- logs
- metrics
- traces

Telemetry powers observability.

---

## Three Pillars Of Observability

### Logs

Human-readable events.

Example:

    User logged in

    Payment failed

---

### Metrics

Numerical measurements.

Example:

    CPU usage

    Request latency

    Error rate

---

### Traces

Track request journeys.

Example:

Request:

    API

↓

    Redis

↓

    PostgreSQL

↓

    Queue

Tracing follows the entire path.

---

## Example: SyncGrid

Request:

    Create charge

Path:

Client

↓

API

↓

Provider

↓

Webhook

Without tracing:

Hard to understand failures.

With tracing:

Entire request visible.

---

## Example: VaultBox

Upload request:

Client

↓

API

↓

Object Storage

↓

Database

↓

Queue

Observability helps identify slow components.

---

## Example: Argus

Argus exists largely because observability is important.

Argus monitors:

- services
- nodes
- health checks
- incidents

Observability is central to its purpose.

---

## Example: NOMMO

NOMMO orchestrates distributed services.

Questions:

- Which worker failed?
- Which node is unhealthy?
- Which deployment caused issues?

Observability provides answers.

---

## Characteristics Of Observable Systems

Observable systems provide:

- visibility
- transparency
- diagnostics
- operational insight

Good systems explain themselves.

---

## Failure Scenario

User reports:

    API is slow

Possible causes:

- Redis issue
- Database issue
- Queue issue
- Network issue

Observability helps locate the actual cause.

---

## Common Mistakes

### Mistake 1

Logging too little.

### Mistake 2

Logging too much.

### Mistake 3

No metrics.

### Mistake 4

No tracing.

### Mistake 5

No dashboards.

---

## Interview Questions

1. What is observability?
2. What is monitoring?
3. Difference between monitoring and observability?
4. What is telemetry?
5. What are the three pillars of observability?
6. Why are traces useful?
7. Why are metrics useful?
8. Why are logs useful?

---

## Exercises

1. Explain observability in your own words.
2. Compare monitoring and observability.
3. Identify telemetry sources in SyncGrid.
4. Identify telemetry sources in VaultBox.
5. Explain why Argus needs observability.

---

## Further Reading

OpenTelemetry

https://opentelemetry.io

Google SRE

https://sre.google

Grafana

https://grafana.com

---

## Summary

Observability is the ability to understand system behavior through telemetry.

The three pillars are:

- logs
- metrics
- traces

Modern production systems rely heavily on observability to maintain reliability.

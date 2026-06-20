# Lesson 03: Metrics & Monitoring

## Learning Objectives

By the end of this lesson you should be able to:

- Explain metrics.
- Understand monitoring systems.
- Identify key service metrics.
- Design dashboards.
- Detect operational issues.

---

## Introduction

Logs explain individual events.

Metrics explain system health.

Example:

Logs:

    Request failed.

Metrics:

    Error rate increased from 0.1% to 15%.

Both are useful.

---

## What Is A Metric?

A metric is a numerical measurement.

Examples:

- CPU usage
- memory usage
- request count
- latency
- error rate

Metrics summarize system behavior.

---

## Why Metrics Matter

Metrics help answer:

- Is the system healthy?
- Is traffic increasing?
- Are errors rising?
- Is latency acceptable?

---

## Four Golden Signals

Google SRE popularized:

### Latency

How long requests take.

---

### Traffic

How much demand exists.

---

### Errors

How many requests fail.

---

### Saturation

How close resources are to limits.

---

## Request Rate

Example:

    500 requests/sec

Useful for capacity planning.

---

## Error Rate

Formula:

    Failed Requests
    ---------------
    Total Requests

Example:

    2%

Error rate

High error rates often indicate incidents.

---

## Latency Percentiles

Average latency can be misleading.

Use:

P50

P95

P99

Example:

P95:

    120ms

Meaning:

95% of requests complete within 120ms.

---

## Infrastructure Metrics

Track:

- CPU
- Memory
- Disk
- Network

Infrastructure problems often impact applications.

---

## Queue Metrics

Monitor:

- queue depth
- failed jobs
- active jobs
- retries

Critical for SyncGrid and inFlowForge.

---

## Database Metrics

Monitor:

- query latency
- connections
- locks
- replication lag

---

## Cache Metrics

Monitor:

- hit ratio
- misses
- memory usage
- evictions

---

## Dashboards

Dashboards provide visibility.

Example:

API Dashboard

- latency
- requests
- errors
- saturation

Single view of service health.

---

## Monitoring Architecture

Applications

↓

Metrics Exporters

↓

Prometheus

↓

Grafana

↓

Dashboards

---

## SyncGrid Example

Monitor:

- provider latency
- webhook failures
- queue depth
- API errors

---

## VaultBox Example

Monitor:

- upload latency
- storage usage
- download success
- quota violations

---

## NOMMO Example

Monitor:

- worker count
- node health
- deployment status
- routing decisions

---

## Common Mistakes

### Mistake 1

Only monitoring CPU.

### Mistake 2

No latency tracking.

### Mistake 3

No queue metrics.

### Mistake 4

No dashboards.

---

## Interview Questions

1. What is a metric?
2. Why monitor latency?
3. Why monitor errors?
4. What are the four golden signals?
5. What is P95 latency?
6. Why are dashboards useful?

---

## Exercises

1. Design a SyncGrid dashboard.
2. Design a VaultBox dashboard.
3. Identify critical metrics for NOMMO.
4. Explain error rate.
5. Explain saturation.

---

## Further Reading

Prometheus

https://prometheus.io

Grafana

https://grafana.com

Google SRE

https://sre.google

---

## Summary

Metrics provide quantitative insight into system health.

Monitoring systems transform metrics into actionable operational visibility.

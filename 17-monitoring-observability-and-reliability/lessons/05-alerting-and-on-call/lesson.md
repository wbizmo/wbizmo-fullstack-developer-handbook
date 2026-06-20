# Lesson 05: Alerting & On-Call

## Learning Objectives

By the end of this lesson you should be able to:

- Explain alerting.
- Design useful alerts.
- Understand alert fatigue.
- Understand on-call responsibilities.
- Build actionable alerting systems.
- Reduce operational noise.

---

## Introduction

Monitoring without alerting is incomplete.

You may have:

- logs
- metrics
- traces

But if nobody notices problems, users suffer.

Alerting bridges monitoring and action.

---

## What Is An Alert?

An alert is a notification generated when a condition is met.

Examples:

- API unavailable
- Error rate exceeds threshold
- Queue backlog growing
- Database replication lag increasing

Alerts help engineers respond quickly.

---

## Why Alerting Matters

Imagine:

SyncGrid webhook queue stops processing.

Monitoring detects issue.

Without alerting:

Nobody notices.

With alerting:

Engineers are informed immediately.

---

## Good Alert Characteristics

Good alerts are:

- actionable
- specific
- relevant
- timely

Bad alerts create noise.

---

## Bad Alert Example

    CPU is 52%

Why is this important?

Nobody knows.

---

## Better Alert Example

    API Error Rate > 10% For 5 Minutes

This indicates a meaningful problem.

---

## Alert Severity

### Informational

Useful but not urgent.

Example:

    New deployment completed

---

### Warning

Potential issue.

Example:

    Queue depth increasing

---

### Critical

Immediate action required.

Example:

    Database unavailable

---

## Alert Fatigue

Too many alerts create problems.

Engineers begin ignoring notifications.

This is alert fatigue.

Dangerous alerts may be missed.

---

## Symptoms Of Alert Fatigue

- muted notifications
- ignored alerts
- delayed responses
- burnout

Reduce noise aggressively.

---

## Actionable Alerts

Every alert should answer:

What happened?

Why does it matter?

What should I do?

---

## Alert Routing

Different alerts go to different teams.

Examples:

Database alerts:

    Platform Team

Payment alerts:

    Payments Team

Infrastructure alerts:

    Operations Team

---

## Escalation Policies

Example:

Level 1:

    On-call engineer

No response:

↓

Level 2:

    Senior engineer

No response:

↓

Level 3:

    Team lead

Escalation improves reliability.

---

## On-Call Responsibilities

On-call engineers:

- receive alerts
- investigate issues
- mitigate incidents
- communicate status
- restore service

---

## Healthy On-Call Culture

Good organizations:

- rotate on-call
- document procedures
- automate repetitive tasks
- reduce noisy alerts

---

## Runbooks

A runbook describes:

What to do when an alert fires.

Example:

Queue backlog alert.

Runbook:

1. Check workers.
2. Check Redis.
3. Check queue metrics.
4. Restart worker if necessary.

---

## SyncGrid Example

Critical alerts:

- webhook failures
- provider outages
- queue backlog

Warning alerts:

- latency increases
- retry spikes

---

## VaultBox Example

Critical alerts:

- storage failures
- database outage

Warning alerts:

- upload latency increase
- quota processing delays

---

## NOMMO Example

Critical alerts:

- node unavailable
- scheduler failure
- routing failure

Warning alerts:

- unhealthy services
- heartbeat delays

---

## Common Mistakes

### Mistake 1

Alerting on everything.

### Mistake 2

No severity levels.

### Mistake 3

No escalation path.

### Mistake 4

No runbooks.

### Mistake 5

Ignoring alert fatigue.

---

## Interview Questions

1. What is alerting?
2. Why is alert fatigue dangerous?
3. What makes an alert actionable?
4. What is on-call?
5. What is a runbook?
6. Why use escalation policies?

---

## Exercises

1. Design alerts for SyncGrid.
2. Design alerts for VaultBox.
3. Design alerts for NOMMO.
4. Create a queue backlog runbook.
5. Explain alert fatigue.

---

## Further Reading

PagerDuty

https://www.pagerduty.com

Grafana Alerting

https://grafana.com

Google SRE

https://sre.google

---

## Summary

Alerting transforms monitoring data into operational action.

Good alerting minimizes noise while maximizing awareness.

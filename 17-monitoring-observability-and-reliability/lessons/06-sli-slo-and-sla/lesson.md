# Lesson 06: SLI, SLO & SLA

## Learning Objectives

By the end of this lesson you should be able to:

- Define SLIs.
- Define SLOs.
- Define SLAs.
- Understand reliability targets.
- Measure service quality.
- Design service objectives.

---

## Introduction

Reliable systems require measurable goals.

Questions:

- How reliable is the service?
- How fast should it be?
- What level of downtime is acceptable?

SLIs, SLOs and SLAs answer these questions.

---

## What Is An SLI?

SLI:

Service Level Indicator.

A measurement.

Examples:

- availability
- latency
- error rate
- success rate

SLIs are raw metrics.

---

## Example SLI

Availability:

    Successful Requests
    -------------------
    Total Requests

Result:

    99.95%

Availability

---

## What Is An SLO?

SLO:

Service Level Objective.

A target.

Example:

    Availability >= 99.9%

The metric is the SLI.

The target is the SLO.

---

## What Is An SLA?

SLA:

Service Level Agreement.

A contractual commitment.

Example:

    99.9% uptime

Failure may trigger:

- credits
- refunds
- penalties

SLAs are business commitments.

---

## Relationship

SLI

↓

SLO

↓

SLA

Measure

↓

Target

↓

Promise

---

## Availability Examples

99%

≈ 3.65 days downtime/year

99.9%

≈ 8.7 hours downtime/year

99.99%

≈ 52 minutes downtime/year

99.999%

≈ 5 minutes downtime/year

---

## Error Budget

Error budget:

Allowed unreliability.

Example:

SLO:

    99.9%

Allowed failure:

    0.1%

Teams can spend this budget on:

- releases
- experiments
- changes

---

## Why Error Budgets Matter

Without error budgets:

Teams may prioritize features over reliability.

Error budgets create balance.

---

## Common SLIs

### Availability

Is service reachable?

### Latency

How fast are requests?

### Error Rate

How many requests fail?

### Durability

Is data preserved?

---

## SyncGrid Example

SLI:

Webhook success rate

SLO:

99.95%

SLA:

99.9%

---

## VaultBox Example

SLI:

Upload success rate

SLO:

99.9%

SLA:

99.5%

---

## NOMMO Example

SLI:

Node heartbeat success

SLO:

99.99%

---

## Choosing SLOs

Too high:

Expensive.

Too low:

Poor user experience.

Balance matters.

---

## Common Mistakes

### Mistake 1

No SLOs.

### Mistake 2

Unrealistic SLOs.

### Mistake 3

Confusing SLIs and SLOs.

### Mistake 4

Ignoring error budgets.

---

## Interview Questions

1. What is an SLI?
2. What is an SLO?
3. What is an SLA?
4. What is an error budget?
5. Why use SLOs?
6. Why are SLAs important?

---

## Exercises

1. Define an SLI for VaultBox.
2. Define an SLO for VaultBox.
3. Define an SLI for SyncGrid.
4. Calculate error budget.
5. Compare SLO and SLA.

---

## Further Reading

Google SRE

https://sre.google

Nobl9

https://www.nobl9.com

---

## Summary

SLIs measure service quality.

SLOs define targets.

SLAs define commitments.

Together they provide reliability goals.

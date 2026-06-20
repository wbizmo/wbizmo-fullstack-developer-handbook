# Lesson 06: Data Management In Microservices

## Learning Objectives

- Understand data ownership.
- Understand database-per-service.
- Understand shared database problems.
- Understand eventual consistency.
- Understand data synchronization.
- Understand CQRS at a high level.

---

## Introduction

Data is one of the hardest aspects of microservices.

In a monolith:

Application

↓

Database

Simple.

In microservices:

Many services.

Many databases.

Coordination becomes difficult.

---

## Shared Database Problem

Common beginner architecture:

Auth Service

↓

Shared Database

Billing Service

↓

Shared Database

Notification Service

↓

Shared Database

Looks convenient.

Creates coupling.

---

## Why Shared Databases Are Dangerous

Problems:

- schema conflicts
- deployment coordination
- ownership confusion
- accidental dependencies

Services stop being independent.

---

## Database Per Service

Preferred approach:

Auth Service

↓

Auth Database

Billing Service

↓

Billing Database

Notification Service

↓

Notification Database

Ownership becomes clear.

---

## Benefits

- autonomy
- independent deployments
- independent scaling
- clearer ownership

---

## Drawbacks

- data duplication
- synchronization complexity
- eventual consistency

---

## Data Ownership

Each service owns its data.

Example:

Billing Service owns:

- invoices
- subscriptions
- payments

Other services should not modify billing tables.

---

## Data Duplication

Sometimes duplication is acceptable.

Example:

Billing Service stores:

user_id

Auth Service stores:

user profile

Each service stores what it needs.

---

## Event Synchronization

Example:

UserUpdated

↓

Event Published

↓

Billing Updates Local Copy

↓

Analytics Updates Local Copy

Common pattern.

---

## Eventual Consistency

Services may temporarily disagree.

Auth Service updated immediately.

Billing Service updates later.

Eventually state converges.

---

## Query Challenges

Question:

How do you generate reports spanning multiple services?

Options:

- API aggregation
- reporting database
- event-driven projections

---

## CQRS

Command Query Responsibility Segregation.

Separate:

Writes

from

Reads

Benefits:

- scalability
- flexibility

Costs:

- complexity

---

## Read Models

Example:

Many services emit events.

↓

Projection Service

↓

Reporting Database

Optimized for queries.

---

## SyncGrid Example

Potential databases:

- Identity DB
- Billing DB
- Provider DB
- Analytics DB

Each owned independently.

---

## VaultBox Example

Potential databases:

- User DB
- Storage Metadata DB
- Billing DB
- Analytics DB

---

## inFlowForge Example

Potential databases:

- Workflow DB
- Execution DB
- Audit DB
- Notification DB

---

## NOMMO Example

Potential databases:

- Registry DB
- Scheduling DB
- Cluster State DB

---

## Common Mistakes

- shared databases
- direct table access
- unclear ownership
- excessive synchronization

---

## Interview Questions

1. Why avoid shared databases?
2. What is database-per-service?
3. What is eventual consistency?
4. What is CQRS?
5. Why does data duplication occur?
6. How would SyncGrid manage data ownership?

---

## Summary

Microservices work best when services own their own data and communicate through APIs or events rather than sharing databases.

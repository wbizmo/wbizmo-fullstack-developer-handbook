# Lesson 04: API Gateways And Edge Services

## Learning Objectives

- Understand API gateways.
- Understand edge services.
- Understand request routing.
- Understand authentication at the edge.
- Understand rate limiting.
- Understand gateway responsibilities.

---

## What Is An API Gateway?

An API Gateway is the entry point into a microservice platform.

Users do not talk directly to:

- Auth Service
- Billing Service
- Notification Service

Instead:

Client

↓

API Gateway

↓

Services

---

## Gateway Responsibilities

Typical responsibilities:

- routing
- authentication
- authorization
- rate limiting
- request validation
- logging
- metrics

---

## Example

Client

↓

Gateway

↓

Auth Service

↓

Billing Service

↓

Provider Service

Gateway simplifies access.

---

## Benefits

- central entry point
- security
- observability
- request control

---

## Drawbacks

- bottleneck risk
- additional latency
- operational complexity

---

## Edge Services

Edge services operate near clients.

Examples:

- API Gateway
- CDN
- Authentication Layer

Purpose:

Protect internal services.

---

## SyncGrid Example

Gateway handles:

- API keys
- JWT validation
- routing
- rate limits

Internal services remain focused.

---

## VaultBox Example

Gateway handles:

- uploads
- authentication
- quota validation

Storage services stay simple.

---

## Common Mistakes

- putting business logic in gateway
- no rate limiting
- no observability

---

## Summary

API Gateways provide a secure and observable entry point into distributed systems.

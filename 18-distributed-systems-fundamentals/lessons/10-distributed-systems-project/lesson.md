# Lesson 10: Distributed Systems Project

## Project

Design a Distributed Service Orchestrator inspired by NOMMO.

This project combines everything learned throughout the module.

You are not expected to build the entire platform.

The goal is architectural thinking.

---

## Project Overview

Build the architecture for a platform capable of:

- node registration
- service deployment
- worker coordination
- service discovery
- heartbeat monitoring
- leader election
- failure detection
- task scheduling
- recovery workflows

---

## Functional Requirements

The system must:

- register workers
- track worker health
- deploy services
- stop services
- restart services
- assign workloads
- monitor cluster state
- recover from failures

---

## Non-Functional Requirements

The system should:

- tolerate node failures
- scale horizontally
- avoid duplicate scheduling
- recover automatically
- maintain cluster visibility
- support thousands of nodes

---

## High-Level Architecture

                Clients
                   |
                   v
             API Gateway
                   |
                   v
            Control Plane
                   |
      --------------------------------
      |              |              |
      v              v              v
   Registry      Scheduler      Monitor
      |              |              |
      --------------------------------
                   |
                   v
            Consensus Layer
                   |
      --------------------------------
      |              |              |
      v              v              v
    Node A        Node B        Node C

---

## Component Responsibilities

### API Gateway

Handles:

- user requests
- authentication
- authorization

---

### Control Plane

Coordinates:

- cluster state
- deployments
- scheduling

---

### Registry

Tracks:

- workers
- services
- health status
- capabilities

---

### Scheduler

Responsible for:

- workload placement
- balancing
- resource allocation

---

### Monitor

Tracks:

- heartbeats
- node health
- failures

---

### Consensus Layer

Maintains:

- cluster agreement
- leadership
- configuration consistency

Potential implementation:

Raft

---

## Node Registration

Worker starts.

↓

Registers with registry.

↓

Receives node ID.

↓

Begins heartbeat transmission.

---

## Heartbeat Flow

Worker

↓

Heartbeat

↓

Monitor

↓

Health Updated

Missed heartbeats trigger investigation.

---

## Service Discovery

Workers register:

- address
- capabilities
- status

Control plane discovers workers dynamically.

No hardcoded addresses.

---

## Leader Election

Cluster nodes participate in elections.

Responsibilities:

- scheduler ownership
- deployment coordination
- state updates

Only one leader active.

---

## Distributed Locks

Used for:

- deployment coordination
- scheduler ownership
- maintenance jobs

Prevents duplicate execution.

---

## Task Scheduling

Deployment request:

↓

Scheduler evaluates cluster.

↓

Node selected.

↓

Deployment assigned.

---

## Failure Detection

Heartbeat missing.

↓

Node suspected failed.

↓

Verification occurs.

↓

Recovery triggered.

---

## Recovery Workflow

Node fails.

↓

Tasks reassigned.

↓

Services restarted.

↓

Cluster stabilized.

---

## Gossip-Based Membership

Optional enhancement.

Nodes exchange:

- health state
- membership information

Improves scalability.

---

## Distributed Transactions

Deployment workflow:

Allocate Resources

↓

Start Service

↓

Register Service

Failure:

Compensation logic executed.

---

## Observability

Collect:

- logs
- metrics
- traces

Monitor:

- deployments
- failures
- scheduler decisions
- node health

---

## Security Considerations

Implement:

- authentication
- authorization
- TLS
- audit logging

Protect cluster operations.

---

## Scaling Strategy

Phase 1:

Single control plane.

---

Phase 2:

Multiple API nodes.

---

Phase 3:

Consensus cluster.

---

Phase 4:

Regional deployment.

---

## Reliability Strategy

Implement:

- retries
- timeouts
- redundancy
- backups
- monitoring

Design for failure.

---

## Trade-Off Analysis

### Centralized Scheduling

Benefits:

- simplicity

Costs:

- bottleneck risk

---

### Distributed Scheduling

Benefits:

- scalability

Costs:

- complexity

---

### Strong Consistency

Benefits:

- correctness

Costs:

- latency

---

### Eventual Consistency

Benefits:

- scalability

Costs:

- temporary disagreement

---

## Deliverables

Create:

1. Requirements document.
2. Architecture diagram.
3. Node lifecycle flow.
4. Heartbeat design.
5. Discovery design.
6. Leader election design.
7. Scheduling strategy.
8. Failure recovery strategy.
9. Observability plan.
10. Trade-off analysis.

---

## Self Assessment

Can you explain:

✓ Heartbeats

✓ Gossip

✓ Service Discovery

✓ Consensus

✓ Leader Election

✓ Distributed Locks

✓ Sagas

✓ Failure Detection

✓ Recovery Workflows

If yes, you now possess a solid foundation in distributed systems.

---

## Summary

This project combines the major concepts of distributed systems:

- coordination
- consensus
- discovery
- scheduling
- recovery
- observability

These same ideas power modern orchestration systems, cloud platforms and large-scale backend infrastructure.

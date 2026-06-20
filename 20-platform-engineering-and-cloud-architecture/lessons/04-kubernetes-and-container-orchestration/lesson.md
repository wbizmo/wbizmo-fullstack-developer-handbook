# Lesson 04: Kubernetes And Container Orchestration

## Learning Objectives

- Understand orchestration.
- Understand Kubernetes.
- Understand Pods.
- Understand Services.
- Understand Deployments.
- Understand cluster management.

---

## Introduction

Containers solve packaging.

Kubernetes solves orchestration.

Question:

How do you manage:

- hundreds of containers
- thousands of deployments
- automatic recovery

Kubernetes provides the answer.

---

## What Is Kubernetes?

Container orchestration platform.

Responsibilities:

- scheduling
- scaling
- networking
- service discovery
- recovery

---

## Cluster

Kubernetes cluster:

Control Plane

↓

Worker Nodes

---

## Pods

Smallest deployable unit.

Usually contains:

- application container
- supporting containers

---

## Deployments

Define desired application state.

Example:

    3 replicas

Kubernetes maintains that state.

---

## Services

Provide stable networking.

Pods may change.

Services provide stable access.

---

## Self-Healing

Container crashes.

↓

Kubernetes restarts it.

Automatically.

---

## Autoscaling

Traffic increases.

↓

Additional replicas created.

---

## NOMMO Connection

NOMMO overlaps conceptually with orchestration concerns:

- scheduling
- health checks
- service placement
- recovery

---

## Summary

Kubernetes is the dominant orchestration platform for modern cloud-native applications.

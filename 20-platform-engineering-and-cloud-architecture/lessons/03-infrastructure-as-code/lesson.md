# Lesson 03: Infrastructure As Code

## Learning Objectives

- Understand Infrastructure as Code (IaC).
- Understand declarative infrastructure.
- Understand reproducibility.
- Understand automation.
- Understand Terraform at a high level.

---

## Introduction

Traditionally infrastructure was created manually.

Engineer:

- creates server
- configures network
- configures database

Manual processes are slow and error-prone.

Infrastructure as Code automates infrastructure management.

---

## What Is Infrastructure As Code?

Infrastructure definitions stored as code.

Example:

Infrastructure described in files.

↓

Version controlled.

↓

Reviewed.

↓

Deployed automatically.

---

## Benefits

- reproducibility
- consistency
- automation
- auditing
- disaster recovery

---

## Declarative Approach

Desired state defined.

Example:

    3 servers
    1 database
    1 load balancer

Tool determines how to create them.

---

## Popular Tools

- Terraform
- Pulumi
- CloudFormation
- OpenTofu

---

## Terraform

Most widely used IaC tool.

Capabilities:

- servers
- networking
- databases
- Kubernetes
- cloud resources

---

## GitOps Relationship

Infrastructure stored in Git.

Changes applied automatically.

Git becomes source of truth.

---

## Platform Engineering Connection

Platform teams often provide:

- infrastructure templates
- deployment blueprints
- reusable modules

---

## NOMMO Connection

Future NOMMO deployments could provision:

- nodes
- clusters
- networking

through IaC workflows.

---

## Summary

Infrastructure as Code transforms infrastructure into repeatable, version-controlled and automated assets.

# Lesson 07: CI/CD Testing Workflows

## Learning Objectives

By the end of this lesson you should be able to:

- Understand CI/CD testing.
- Explain automated pipelines.
- Run tests before deployment.
- Understand deployment gates.
- Build reliable release workflows.

## What Is CI?

CI means:

    Continuous Integration

Developers frequently merge code.

Automated systems verify changes.

## What Is CD?

CD means:

    Continuous Delivery

or

    Continuous Deployment

Code automatically moves toward production.

## Why Testing Matters In CI/CD

Without testing:

Broken code can reach production.

With testing:

Failures are detected early.

## Typical Workflow

Developer Pushes Code

↓

GitHub

↓

Tests Run

↓

Build Runs

↓

Deployment Happens

## Example Pipeline

Step 1

Install dependencies

Step 2

Run linting

Step 3

Run tests

Step 4

Build project

Step 5

Deploy

## GitHub Actions Example

    name: CI

    on:
      push:

    jobs:
      test:
        runs-on: ubuntu-latest

        steps:
          - uses:
              actions/checkout@v4

          - uses:
              actions/setup-node@v4

          - run:
              npm install

          - run:
              npm test

## Deployment Gates

Deployment should stop if:

- Tests fail
- Build fails
- Security checks fail

## Real World Examples

Argus:

Protocol tests before release.

NOMMO:

Distributed-system verification.

SyncGrid:

API testing before deployment.

VaultBox:

Authentication testing before deployment.

## Common Mistakes

- Deploying without tests.
- Ignoring failed pipelines.
- Testing only manually.
- No rollback strategy.

## Exercises

1. Define CI.
2. Define CD.
3. Draw deployment pipeline.
4. Explain deployment gates.
5. Create simple GitHub Action.

## Summary

Testing integrated into CI/CD dramatically improves reliability and deployment confidence.

## References

https://docs.github.com/actions

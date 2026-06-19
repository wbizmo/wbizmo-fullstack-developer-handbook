# Lesson 09: Scheduled Jobs and Workers

## Learning Objectives

By the end of this lesson you should be able to:

- Schedule jobs.
- Build workers.
- Understand recurring tasks.
- Automate operations.
- Design background systems.

## Scheduled Jobs

Some work happens automatically.

Examples:

- Daily reports
- Weekly emails
- Cleanup tasks
- Analytics generation

## Delayed Jobs

Example:

    await queue.add(
      "email",
      data,
      {
        delay: 60000
      }
    );

Runs after:

    60 seconds

## Recurring Jobs

Example:

Daily billing check.

Nightly backups.

Weekly reports.

## Worker Responsibilities

Workers:

- Consume jobs
- Process jobs
- Handle failures
- Report status

## Worker Architecture

Producer

↓

Queue

↓

Worker

↓

Result

## Scaling Workers

One worker:

Limited throughput.

Multiple workers:

Higher throughput.

Example:

Worker 1

Worker 2

Worker 3

All consuming jobs.

## Monitoring Workers

Track:

- active jobs
- failed jobs
- completed jobs
- queue depth

## Real World Examples

SyncGrid:

Webhook processors.

VaultBox:

Storage jobs.

inFlowForge:

Workflow execution workers.

Argus:

Monitoring workers.

NOMMO:

Control plane workers.

## Common Mistakes

- Single worker bottlenecks.
- No monitoring.
- No retries.
- No scheduling strategy.

## Exercises

1. Create delayed job.
2. Explain recurring jobs.
3. Explain worker scaling.
4. Explain monitoring.
5. Draw worker architecture.

## Interview Questions

1. What is a worker?
2. Why schedule jobs?
3. Why scale workers?
4. What metrics should be monitored?

## Summary

Scheduled jobs automate system tasks and workers execute them reliably.

## References

https://docs.bullmq.io/guide/jobs/delayed

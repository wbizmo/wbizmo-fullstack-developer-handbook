# Lesson 08: Retries, Failures and Dead Letter Queues

## Learning Objectives

By the end of this lesson you should be able to:

- Handle failures.
- Configure retries.
- Understand backoff strategies.
- Understand dead letter queues.
- Improve reliability.

## Failures Happen

External services fail.

Examples:

- Email providers
- Payment gateways
- Webhooks
- APIs

Queues must handle failure gracefully.

## Retry Example

    await queue.add(
      "send-email",
      data,
      {
        attempts: 5
      }
    );

BullMQ retries automatically.

## Why Retry?

Temporary failures often recover.

Examples:

- Network issues
- Rate limits
- Timeouts

## Backoff

Instead of retrying instantly:

Wait between attempts.

Example:

    await queue.add(
      "job",
      data,
      {
        attempts: 5,
        backoff: {
          type: "exponential",
          delay: 1000
        }
      }
    );

## Dead Letter Queue

DLQ stores permanently failed jobs.

Flow:

Job

↓

Retry

↓

Retry

↓

Retry

↓

Fail

↓

DLQ

## Why Use DLQ?

Benefits:

- Investigation
- Recovery
- Auditing

## Monitoring Failed Jobs

Track:

- failure reason
- attempts
- timestamps
- job payload

## Real World Examples

SyncGrid:

Failed webhooks.

VaultBox:

Failed file processing.

inFlowForge:

Failed workflow execution.

## Common Mistakes

- No retries.
- Infinite retries.
- No monitoring.
- No DLQ.

## Exercises

1. Configure retries.
2. Configure backoff.
3. Explain DLQ.
4. Explain monitoring.
5. Explain failure recovery.

## Interview Questions

1. Why retry jobs?
2. What is exponential backoff?
3. What is a DLQ?
4. Why monitor failures?

## Summary

Reliable systems assume failures will happen.

Retries and DLQs improve resilience.

## References

https://docs.bullmq.io/guide/retrying-failing-jobs

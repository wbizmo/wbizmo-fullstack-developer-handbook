# Lesson 06: Background Jobs and Queues

## Learning Objectives

By the end of this lesson you should be able to:

- Explain queues.
- Explain background jobs.
- Understand producers and workers.
- Understand asynchronous processing.
- Design job workflows.

## Why Background Jobs Exist

Some tasks take time:

- Sending email
- Processing files
- Generating reports
- Calling external APIs

Users should not wait.

## Without Queue

Request

↓

Send Email

↓

Generate PDF

↓

Call API

↓

Response

Slow.

## With Queue

Request

↓

Create Job

↓

Return Response

↓

Worker Processes Job

Fast.

## Queue Architecture

Producer

↓

Queue

↓

Worker

## Producer Example

    await queue.add(
      "send-email",
      {
        email: "user@example.com"
      }
    );

## Worker Example

    worker.process(
      async (job) => {
        console.log(
          job.data.email
        );
      }
    );

## Benefits

- Faster responses
- Scalability
- Reliability
- Retry support

## Common Job Types

- Email
- Notifications
- Billing
- Reports
- Imports
- Exports

## Portfolio Examples

SyncGrid:

Webhook delivery.

VaultBox:

File processing.

inFlowForge:

Workflow execution.

Argus:

Monitoring tasks.

NOMMO:

Distributed orchestration jobs.

## Common Mistakes

- Long-running HTTP requests.
- No retry logic.
- No monitoring.
- No failure handling.

## Exercises

1. Define queue.
2. Define worker.
3. Define producer.
4. Explain async processing.
5. Explain queue benefits.

## Interview Questions

1. Why use queues?
2. What is a worker?
3. What is asynchronous processing?
4. What jobs belong in queues?

## Summary

Queues allow applications to perform slow work asynchronously.

## References

https://docs.bullmq.io

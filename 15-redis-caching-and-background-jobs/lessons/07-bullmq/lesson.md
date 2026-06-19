# Lesson 07: BullMQ

## Learning Objectives

By the end of this lesson you should be able to:

- Explain BullMQ.
- Create queues.
- Add jobs.
- Create workers.
- Process background tasks.

## What Is BullMQ?

BullMQ is a Redis-based job queue for Node.js.

It is commonly used for:

- Emails
- Notifications
- Webhooks
- Reports
- Scheduled tasks

## Install

    npm install bullmq

## Queue Example

    import { Queue }
      from "bullmq";

    const emailQueue =
      new Queue(
        "emails",
        {
          connection: {
            host: "localhost",
            port: 6379
          }
        }
      );

## Add Job

    await emailQueue.add(
      "welcome-email",
      {
        email:
          "user@example.com"
      }
    );

## Worker Example

    import { Worker }
      from "bullmq";

    const worker =
      new Worker(
        "emails",
        async (job) => {
          console.log(
            job.data.email
          );
        }
      );

## Job Object

Contains:

- id
- name
- data
- attempts
- timestamp

## Why BullMQ?

Benefits:

- Redis-backed
- Retries
- Delays
- Scheduling
- Scalability

## Real World Examples

SyncGrid:

Webhook queue.

inFlowForge:

Workflow execution.

VaultBox:

File processing.

## Common Mistakes

- No monitoring.
- No retries.
- Single worker only.
- Ignoring failures.

## Exercises

1. Install BullMQ.
2. Create queue.
3. Add job.
4. Create worker.
5. Process job.

## Interview Questions

1. What is BullMQ?
2. Why use BullMQ?
3. What is a worker?
4. What is a queue?

## Summary

BullMQ is one of the most popular queue systems in the Node.js ecosystem.

## References

https://docs.bullmq.io

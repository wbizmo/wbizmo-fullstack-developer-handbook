# Lesson 06: Events, Event Loop and Async Programming

## Learning Objectives

By the end of this lesson, you should be able to:

- Understand events in Node.js.
- Understand EventEmitter.
- Understand async programming in Node.js.
- Understand the event loop at a practical level.
- Use timers.
- Explain why Node.js is non-blocking.

## What Are Events?

An event is something that happens.

Examples:

- A user connects
- A file finishes reading
- A request arrives
- A timer completes
- A stream receives data

Node.js is event-driven.

That means many parts of Node.js respond to events.

## EventEmitter

Node.js includes an EventEmitter class.

Import:

    import { EventEmitter } from "node:events";

Example:

    import { EventEmitter } from "node:events";

    const emitter = new EventEmitter();

    emitter.on("userCreated", (user) => {
      console.log("New user:", user);
    });

    emitter.emit("userCreated", {
      id: "1",
      name: "Ada"
    });

## on

Registers a listener.

    emitter.on("eventName", callback);

## emit

Triggers an event.

    emitter.emit("eventName", data);

## Why Events Matter

Events are useful for:

- Logging
- Notifications
- Background tasks
- Application lifecycle
- Real-time systems
- WebSocket-style communication

## Async Programming

Node.js often performs operations that take time.

Examples:

- Reading files
- Calling APIs
- Querying databases
- Uploading files
- Sending emails

Instead of blocking everything, Node.js continues running other work.

## Non-Blocking Behavior

Example:

    console.log("Start");

    setTimeout(() => {
      console.log("Timer finished");
    }, 1000);

    console.log("End");

Output:

    Start
    End
    Timer finished

## Event Loop

The event loop allows Node.js to handle async tasks.

Simple explanation:

Node.js runs normal code first.

When async tasks finish, callbacks are placed in a queue.

The event loop picks them up when the call stack is clear.

## Mini Project

Build a task event logger.

Features:

- Emit taskCreated
- Emit taskCompleted
- Listen and log events

## Exercises

1. Create an EventEmitter.
2. Listen for a userCreated event.
3. Emit userCreated.
4. Create taskCreated and taskCompleted events.
5. Use setTimeout to simulate delayed work.
6. Explain non-blocking behavior.

## Summary

Node.js is event-driven.

EventEmitter allows custom events.

The event loop enables async non-blocking behavior.

## References

https://nodejs.org/api/events.html

https://nodejs.org/en/learn/asynchronous-work/event-loop-timers-and-nexttick

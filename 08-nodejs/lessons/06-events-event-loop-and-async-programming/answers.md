# Lesson 06 Answers

1. Something that happens.
2. A Node.js class for creating and listening to events.
3. Registers an event listener.
4. Triggers an event.
5. Other work can continue while waiting.
6. Runs code after a delay.
7. A mechanism that handles async callbacks.
8. File reading, API calls, database queries.
9. It prevents blocking while slow tasks complete.
10. Logging, notifications, task lifecycle.

## Mini Project Solution

task-events.js

    import { EventEmitter } from "node:events";

    const taskEvents = new EventEmitter();

    taskEvents.on("taskCreated", (task) => {
      console.log("Task created:", task.title);
    });

    taskEvents.on("taskCompleted", (task) => {
      console.log("Task completed:", task.title);
    });

    const task = {
      id: "task_1",
      title: "Learn Node.js events"
    };

    taskEvents.emit("taskCreated", task);

    setTimeout(() => {
      taskEvents.emit("taskCompleted", task);
    }, 1000);

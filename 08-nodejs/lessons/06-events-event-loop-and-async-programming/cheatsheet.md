# Lesson 06 Cheatsheet

Import:

    import { EventEmitter } from "node:events";

Create:

    const emitter = new EventEmitter();

Listen:

    emitter.on("event", callback);

Emit:

    emitter.emit("event", data);

Timer:

    setTimeout(() => {}, 1000);

Key takeaway:
    Node.js uses events and async behavior to handle work efficiently.

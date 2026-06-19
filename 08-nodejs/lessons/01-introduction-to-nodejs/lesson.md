# Lesson 01: Introduction To Node.js

## Learning Objectives

By the end of this lesson, you should be able to:

- Explain what Node.js is.
- Explain why Node.js exists.
- Explain the difference between browser JavaScript and Node.js.
- Understand common Node.js use cases.
- Run your first Node.js program.

## What Is Node.js?

Node.js is a JavaScript runtime.

It allows JavaScript to run outside the browser.

Before Node.js:

JavaScript mostly lived inside browsers.

After Node.js:

JavaScript could be used to build:

- APIs
- Web servers
- CLIs
- Automation scripts
- Build tools
- Desktop applications
- Real-time systems

## Who Created Node.js?

Node.js was created by:

    Ryan Dahl

Initial release:

    2009

## Why Was Node.js Created?

Web applications needed servers.

Most developers already knew JavaScript.

Node.js allowed developers to use one language across:

Frontend:

    JavaScript

Backend:

    JavaScript

## Browser JavaScript vs Node.js

Browser:

- DOM
- window
- document

Node.js:

- File system
- Network access
- Operating system access
- Process management

Example:

Browser:

    document.querySelector()

Node:

    fs.readFile()

## What Can Node.js Build?

Examples:

- REST APIs
- Fastify applications
- Express applications
- CMS platforms
- Developer tools
- Workflow engines
- CLI tools
- Automation platforms

Examples from your portfolio:

- SyncGrid API
- inFlowForge API
- VaultBox API
- LaunchStack CLI
- Argus

## Running Node.js

Create:

    app.js

Content:

    console.log("Hello Node.js");

Run:

    node app.js

Output:

    Hello Node.js

## Node.js Architecture

Node.js is:

- Event driven
- Non-blocking
- Single threaded
- Highly scalable

We will study these concepts later.

## Advantages

- Huge ecosystem
- JavaScript everywhere
- Fast development
- Excellent tooling
- Large community

## Limitations

- CPU-heavy workloads may require special handling.
- Not every workload benefits from Node.js.

## Hands-On Exercise

Create:

    hello.js

Print:

    Hello Node.js

Print:

    Your name

Print:

    Today's date

## Mini Challenge

Create:

    profile.js

Output:

    Name
    Location
    Favorite Language
    Career Goal

using console.log().

## Summary

Node.js is a JavaScript runtime.

It allows JavaScript to run outside browsers.

It powers many modern backend systems.

## References

https://nodejs.org/en/docs

https://nodejs.org/en/about

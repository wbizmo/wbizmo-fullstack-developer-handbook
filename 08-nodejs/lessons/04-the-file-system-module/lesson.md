# Lesson 04: The File System Module

## Learning Objectives

By the end of this lesson, you should be able to:

- Understand the fs module.
- Read files.
- Write files.
- Append data.
- Delete files.
- Work with JSON files.
- Build a simple file-based application.

## What Is The File System Module?

Node.js includes a built-in module called:

    fs

It allows applications to interact with files and folders.

Examples:

- Read files
- Write files
- Update files
- Delete files
- Create folders
- Manage data

No installation required.

## Importing fs

Modern syntax:

    import fs from "node:fs";

Promise version:

    import fs from "node:fs/promises";

## Reading Files

Create:

    notes.txt

Content:

    Learn Node.js

Read:

    import fs from "node:fs/promises";

    const content =
      await fs.readFile(
        "notes.txt",
        "utf8"
      );

    console.log(content);

Output:

    Learn Node.js

## Writing Files

Example:

    await fs.writeFile(
      "notes.txt",
      "Hello World"
    );

Creates file if it doesn't exist.

Replaces content if it does.

## Appending Data

Example:

    await fs.appendFile(
      "notes.txt",
      "\nLearn Fastify"
    );

Output:

    Hello World
    Learn Fastify

## Deleting Files

Example:

    await fs.unlink(
      "notes.txt"
    );

File removed.

## Creating Directories

Example:

    await fs.mkdir(
      "logs"
    );

Recursive:

    await fs.mkdir(
      "storage/files",
      { recursive: true }
    );

## Reading JSON

users.json

    [
      {
        "id": 1,
        "name": "Ada"
      }
    ]

Read:

    const content =
      await fs.readFile(
        "users.json",
        "utf8"
      );

    const users =
      JSON.parse(content);

## Writing JSON

Example:

    const users = [
      {
        id: 1,
        name: "Ada"
      }
    ];

    await fs.writeFile(
      "users.json",
      JSON.stringify(
        users,
        null,
        2
      )
    );

## Why JSON Files Matter

Many beginner applications use:

- JSON databases
- Config files
- Local storage
- Cached data

Before learning SQL databases, file storage teaches valuable concepts.

## Real Project Example

A simple note-taking application:

Files:

    notes.json

Operations:

- Add note
- Delete note
- List notes
- Search notes

This is a small database.

## Mini Project

Build:

    notes-manager.js

Features:

- Add note
- List notes

Data stored inside:

    notes.json

## Example Solution

    import fs from "node:fs/promises";

    async function addNote(
      text
    ) {
      const content =
        await fs.readFile(
          "notes.json",
          "utf8"
        );

      const notes =
        JSON.parse(content);

      notes.push(text);

      await fs.writeFile(
        "notes.json",
        JSON.stringify(
          notes,
          null,
          2
        )
      );
    }

## Common Beginner Mistakes

### Mistake 1

Forgetting:

    await

### Mistake 2

Not handling missing files.

### Mistake 3

Writing invalid JSON.

### Mistake 4

Reading huge files into memory unnecessarily.

## Exercises

1. Create notes.txt.
2. Read notes.txt.
3. Append new content.
4. Delete notes.txt.
5. Create users.json.
6. Read users.json.
7. Write users.json.
8. Build a simple notes manager.

## Summary

The fs module allows Node.js applications to interact with files.

File storage teaches concepts used later in databases and APIs.

## References

https://nodejs.org/api/fs.html

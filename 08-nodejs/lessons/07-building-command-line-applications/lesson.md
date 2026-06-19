# Lesson 07: Building Command Line Applications

## Learning Objectives

By the end of this lesson, you should be able to:

- Understand CLI applications.
- Read command line arguments.
- Use process.argv.
- Build a simple CLI tool.
- Understand CLI project structure.

## What Is A CLI?

CLI means Command Line Interface.

A CLI is a program used from the terminal.

Examples:

- git
- npm
- node
- vite
- ts-node
- launchstack

Your LaunchStack CLI is an example of a developer tool built for terminal workflows.

## process.argv

Node.js exposes command line arguments through:

    process.argv

Example:

    console.log(process.argv);

Run:

    node app.js hello world

Output includes:

- Node path
- File path
- hello
- world

## Getting User Arguments

Example:

    const command = process.argv[2];

    console.log(command);

Run:

    node app.js greet

command becomes:

    greet

## Simple CLI

    const command = process.argv[2];

    if (command === "hello") {
      console.log("Hello from CLI");
    } else {
      console.log("Unknown command");
    }

## Mini Project

Build:

    notes-cli.js

Commands:

    add
    list

Example:

    node notes-cli.js add "Learn Node.js"

    node notes-cli.js list

Store data in:

    notes.json

## CLI Structure

Simple:

    notes-cli.js
    notes.json

Better:

    src/
      cli.js
      notes.js
      storage.js

## Common CLI Features

- Commands
- Flags
- Help text
- Version output
- Config files
- File operations

## Exercises

1. Print process.argv.
2. Read command from process.argv[2].
3. Create hello command.
4. Create add command.
5. Create list command.
6. Store notes in notes.json.

## Summary

CLI tools allow users to run programs from the terminal.

Node.js is excellent for building CLIs.

process.argv gives access to terminal arguments.

## References

https://nodejs.org/api/process.html

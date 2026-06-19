# Lesson 02: Computers and Operating Systems

## Learning Objectives

By the end of this lesson, you should be able to:

- Explain what a computer is.
- Identify the major parts of a computer.
- Understand the difference between hardware and software.
- Explain what an operating system does.
- Identify common operating systems.
- Understand why developers must understand their operating system.

## What Is a Computer?

A computer is an electronic machine that receives input, processes data, stores information, and produces output.

A simple way to think about a computer:

    Input → Processing → Storage → Output

Example:

You type a message on your keyboard.

The computer processes the characters.

The message is stored in memory or on disk.

The message appears on your screen.

## The Four Basic Computer Operations

### 1. Input

Input is data given to the computer.

Examples:

- Keyboard typing
- Mouse clicks
- Touchscreen taps
- Microphone audio
- Camera images

### 2. Processing

Processing is what the computer does with input.

The CPU handles most processing tasks.

Examples:

- Calculating numbers
- Running code
- Opening applications
- Rendering a webpage

### 3. Storage

Storage is where data is kept.

There are two major kinds:

- Temporary storage
- Permanent storage

Temporary storage usually means RAM.

Permanent storage usually means SSD or HDD.

### 4. Output

Output is the result produced by the computer.

Examples:

- Text on a screen
- Sound from speakers
- Printed paper
- Saved files

## Major Parts of a Computer

### CPU

CPU means Central Processing Unit.

It is often called the brain of the computer because it executes instructions.

When you run a program, the CPU processes the instructions.

### RAM

RAM means Random Access Memory.

RAM temporarily stores data that active programs need.

If you open VS Code, Chrome, and a terminal, they all use RAM.

When the computer turns off, most data in RAM disappears.

### Storage

Storage keeps files permanently until you delete them.

Examples:

- SSD
- HDD
- USB drive
- Memory card

Your projects, photos, videos, and applications are stored here.

### Motherboard

The motherboard connects the major parts of the computer.

The CPU, RAM, storage, and other components communicate through it.

### GPU

GPU means Graphics Processing Unit.

It helps process graphics, videos, games, animations, and some AI workloads.

### Input Devices

Input devices allow users to send information into the computer.

Examples:

- Keyboard
- Mouse
- Microphone
- Scanner
- Camera

### Output Devices

Output devices allow the computer to show or produce results.

Examples:

- Monitor
- Speaker
- Printer
- Headphones

## Hardware vs Software

Hardware is the physical part of a computer.

Software is the set of instructions that runs on hardware.

Examples of hardware:

- Keyboard
- Mouse
- Monitor
- CPU
- RAM

Examples of software:

- Windows
- Chrome
- VS Code
- WhatsApp
- Node.js

A useful way to remember:

    Hardware is what you can touch.
    Software is what tells hardware what to do.

## What Is an Operating System?

An operating system is the main software that manages a computer.

It controls hardware, runs applications, manages files, and provides a user interface.

Without an operating system, most users would not be able to easily interact with a computer.

## Common Operating Systems

### Windows

Windows is widely used on personal computers.

Many beginners learn development on Windows.

Common developer tools on Windows include:

- PowerShell
- Command Prompt
- Git Bash
- Windows Terminal
- VS Code

### macOS

macOS is Apple's operating system for Mac computers.

It is popular among many designers, developers, and creative professionals.

Its terminal uses Unix-like commands.

### Linux

Linux is a family of open-source operating systems.

It is extremely important in backend development, cloud computing, servers, DevOps, and infrastructure.

Many web servers run Linux.

Popular Linux distributions include:

- Ubuntu
- Debian
- Fedora
- Arch Linux

### Android

Android is an operating system for mobile devices.

It is based on Linux.

### iOS

iOS is Apple's operating system for iPhones.

## Why Developers Should Understand Operating Systems

Developers work with files, folders, commands, permissions, environment variables, software installations, processes, and networks.

All of these are controlled by the operating system.

A developer who understands the operating system will have fewer problems when:

- Installing tools
- Running commands
- Managing project folders
- Fixing permission errors
- Using Git
- Running local servers
- Deploying applications
- Debugging environment issues

## Files and Applications

Every application installed on your computer lives somewhere in the file system.

For example:

- VS Code is an application.
- Your project is a folder.
- Your code files live inside that folder.
- The terminal lets you navigate and control those files.

This is why learning files, folders, and paths is important.

## Processes

A process is a running program.

When you open Chrome, your operating system starts a Chrome process.

When you run a Node.js server, your operating system starts a Node process.

Developers often need to understand processes when:

- A server is already using a port
- An application freezes
- A command keeps running
- A background task needs to stop

## Permissions

Operating systems protect files and actions using permissions.

Permissions decide who can:

- Read a file
- Write to a file
- Execute a file
- Install software
- Delete folders

Permission issues are common in development.

## Environment Variables

Environment variables are values stored by the operating system and used by programs.

Examples:

- API keys
- Database URLs
- Secret tokens
- Port numbers

A backend project might use an environment variable like:

    PORT=4000

This tells the application which port to run on.

## Common Beginner Mistakes

### Mistake 1: Installing tools from random websites

Always download developer tools from official websites.

### Mistake 2: Not knowing where files are saved

Always know your project location.

### Mistake 3: Confusing RAM and storage

RAM is temporary memory.

Storage is long-term file storage.

### Mistake 4: Ignoring the terminal

The terminal is one of the most important developer tools.

### Mistake 5: Thinking the operating system does not matter

It matters a lot. Commands, paths, permissions, and tools can behave differently across Windows, macOS, and Linux.

## Exercises

### Exercise 1

List the operating system you currently use.

### Exercise 2

Write three examples of hardware.

### Exercise 3

Write three examples of software.

### Exercise 4

Explain the difference between RAM and storage.

### Exercise 5

Open your computer's file manager and locate your Documents or Downloads folder.

### Exercise 6

Find one application installed on your computer and identify whether it is software or hardware.

### Exercise 7

Explain why developers should know how their operating system works.

## Did You Know?

Most websites and APIs you use every day are hosted on servers running Linux.

Even if you use Windows as your personal computer, learning some Linux-style commands will help you later in backend development and deployment.

## Fun Fact

The word "computer" originally referred to people who performed calculations manually before electronic computers became common.

## Summary

A computer receives input, processes data, stores information, and produces output.

Hardware refers to physical components.

Software refers to programs and instructions.

The operating system manages hardware, applications, files, permissions, processes, and user interaction.

Developers need operating system knowledge because modern software development depends heavily on files, terminals, processes, permissions, and installed tools.

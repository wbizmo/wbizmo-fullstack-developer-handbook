# Lesson 05: Terminal, PowerShell and Git Bash

## Learning Objectives

By the end of this lesson, you should be able to:

- Understand what a terminal is.
- Explain what a shell is.
- Understand the difference between PowerShell, Command Prompt, and Git Bash.
- Navigate directories using terminal commands.
- Create and delete files and folders.
- Understand why developers use terminals.

## What Is a Terminal?

A terminal is an application that allows you to communicate with your operating system using text commands.

Instead of clicking buttons, you type instructions.

Example:

    mkdir project

The operating system receives the instruction and creates a folder.

## Why Developers Use Terminals

Many development tools are designed to be used from the terminal.

Examples:

- Git
- Node.js
- npm
- Docker
- Database tools
- Deployment tools

Terminals are often faster than graphical interfaces.

## What Is a Shell?

A shell is the program that interprets commands entered into a terminal.

The terminal displays the interface.

The shell processes commands.

Think of it like this:

    You → Terminal → Shell → Operating System

## Common Windows Shells

### Command Prompt (CMD)

One of the oldest Windows command-line tools.

Example:

    dir

Lists files and folders.

### PowerShell

A more advanced shell developed by Microsoft.

PowerShell can work with:

- Files
- Processes
- Services
- Objects

Example:

    Get-ChildItem

Lists files and folders.

### Git Bash

Git Bash provides a Unix-style shell for Windows.

Many tutorials use Git Bash because Linux and macOS use similar commands.

Example:

    ls

Lists files and folders.

## Opening PowerShell

Method 1:

Press:

    Windows + X

Select:

    Windows PowerShell

or

    Terminal

Method 2:

Search:

    PowerShell

in the Start Menu.

## Opening Git Bash

After installing Git:

Right-click inside a folder.

Select:

    Git Bash Here

## Navigating Directories

### Current Directory

PowerShell:

    Get-Location

Git Bash:

    pwd

Shows your current location.

## Listing Files

PowerShell:

    Get-ChildItem

Alias:

    ls

CMD:

    dir

Git Bash:

    ls

## Changing Directories

PowerShell:

    Set-Location Documents

Alias:

    cd Documents

Git Bash:

    cd Documents

## Moving Up One Folder

PowerShell:

    cd ..

Git Bash:

    cd ..

The two dots mean:

    Parent directory

## Creating Folders

PowerShell:

    mkdir my-project

Git Bash:

    mkdir my-project

Creates:

    my-project

## Creating Files

PowerShell:

    New-Item notes.txt

Git Bash:

    touch notes.txt

Creates:

    notes.txt

## Deleting Files

PowerShell:

    Remove-Item notes.txt

Git Bash:

    rm notes.txt

Deletes:

    notes.txt

## Deleting Folders

PowerShell:

    Remove-Item foldername -Recurse

Git Bash:

    rm -rf foldername

Be careful.

Deleted files may not be recoverable.

## Clearing the Screen

PowerShell:

    clear

Git Bash:

    clear

## Viewing File Contents

PowerShell:

    Get-Content notes.txt

Git Bash:

    cat notes.txt

Displays file contents.

## Running Programs

Example:

    node app.js

Runs a Node.js program.

## Why Developers Love the Terminal

Benefits:

- Faster workflows
- Automation
- Scripting
- Tool integration
- Remote server management

Most backend and DevOps work relies heavily on terminal usage.

## Common Beginner Mistakes

### Mistake 1

Running commands in the wrong folder.

### Mistake 2

Deleting files accidentally.

### Mistake 3

Not understanding relative paths.

### Mistake 4

Ignoring terminal error messages.

### Mistake 5

Copying commands without understanding them.

## Exercises

### Exercise 1

Open PowerShell.

### Exercise 2

Check your current directory.

### Exercise 3

Create a folder called:

    practice

### Exercise 4

Create a file called:

    notes.txt

inside practice.

### Exercise 5

View the file.

### Exercise 6

Delete the file.

### Exercise 7

Delete the folder.

### Exercise 8

Navigate into your project folder.

### Exercise 9

Navigate back out.

### Exercise 10

Explain the difference between PowerShell and Git Bash.

## Did You Know?

Many cloud servers have no graphical interface at all. Administrators manage them entirely through terminals.

## Fun Fact

Some developers spend entire workdays inside terminals and rarely touch the mouse.

## Summary

A terminal allows you to communicate with your operating system using commands.

PowerShell, CMD, and Git Bash are common shells used by developers.

Understanding terminal navigation, file management, and commands is a critical skill for modern software development.

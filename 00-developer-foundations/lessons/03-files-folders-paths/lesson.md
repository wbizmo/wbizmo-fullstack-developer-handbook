# Lesson 03: Files, Folders and Paths

## Learning Objectives

By the end of this lesson, you should be able to:

- Explain what files and folders are.
- Understand directory structures.
- Understand file extensions.
- Explain absolute and relative paths.
- Navigate directories confidently.
- Understand why paths are important in software development.

## What Is a File?

A file is a collection of information stored on a computer.

Examples:

- report.docx
- photo.jpg
- video.mp4
- index.html
- app.js
- README.md

Files store data.

Different file types store different kinds of data.

## What Is a Folder?

A folder is a container used to organize files and other folders.

Example:

    Documents/
        Resume.docx
        Notes.txt

Folders help keep information organized.

Folders are also called directories.

## Why Organization Matters

Imagine having:

    10 files

Finding one file is easy.

Now imagine:

    50,000 files

Without folders, locating anything becomes difficult.

Developers use folder structures to keep projects organized.

## Example Project Structure

    my-project/
        index.html
        styles.css
        script.js

A larger project:

    my-app/
        src/
        public/
        tests/
        docs/
        package.json

## File Names

A file name usually contains:

    filename.extension

Example:

    app.js

Filename:

    app

Extension:

    js

## Common File Extensions

Web Development:

    .html
    .css
    .js
    .ts

Documentation:

    .md
    .txt

Images:

    .png
    .jpg
    .svg
    .gif

Data:

    .json
    .csv

Programming:

    .py
    .php
    .java
    .go

## What Is a Path?

A path tells the operating system where a file or folder is located.

Think of it like a home address.

Example:

    C:\Users\Williams\Documents\notes.txt

The operating system uses the path to locate the file.

## Absolute Paths

An absolute path starts from the root location.

Windows example:

    C:\Users\Williams\Documents\project

Linux example:

    /home/williams/project

Absolute paths always point to a specific location.

## Relative Paths

A relative path starts from your current location.

Example:

    documents/report.txt

or

    ./documents/report.txt

Relative paths are shorter and commonly used in development.

## Current Directory

Your current directory is the folder you are currently working in.

Example:

    C:\Projects

If your current directory is:

    C:\Projects

and you access:

    app.js

the computer looks for:

    C:\Projects\app.js

## Parent Directory

The parent directory is the folder above the current folder.

Example:

    Projects/
        Website/
            index.html

Website's parent directory is:

    Projects

## Special Path Symbols

Current folder:

    .

Parent folder:

    ..

Examples:

    ./app.js

    ../README.md

These symbols are heavily used in development.

## Why Developers Care About Paths

Paths are everywhere.

Examples:

- Importing files
- Loading images
- Accessing configuration files
- Reading databases
- Running scripts
- Deploying applications

Incorrect paths are one of the most common beginner errors.

## Example

HTML:

    <img src="images/logo.png">

The browser follows the path to locate the image.

If the image path is wrong:

    Broken image

## Common Beginner Mistakes

### Mistake 1

Confusing files with folders.

### Mistake 2

Renaming file extensions accidentally.

Example:

    app.js.txt

instead of

    app.js

### Mistake 3

Using incorrect paths.

Example:

    ./image.png

when the image actually exists in:

    ./images/image.png

### Mistake 4

Not knowing the current directory.

Many terminal errors occur because you are in the wrong folder.

## Exercises

### Exercise 1

List five file extensions you have seen before.

### Exercise 2

Create a folder called:

    learning

Inside it create:

    notes.txt

### Exercise 3

Explain the difference between a file and a folder.

### Exercise 4

Explain the difference between an absolute path and a relative path.

### Exercise 5

Draw a simple folder structure for a website.

### Exercise 6

What does:

    ..

mean?

### Exercise 7

What does:

    .

mean?

## Did You Know?

Modern operating systems may contain millions of files. Your operating system uses file systems to organize and locate them efficiently.

## Fun Fact

Many developers spend more time navigating files and folders than writing code during certain debugging sessions.

## Summary

Files store information.

Folders organize files.

Paths tell the operating system where files are located.

Developers use paths constantly when building software, loading resources, running programs, and deploying applications.

Understanding files, folders, and paths is one of the most important foundational skills in software development.

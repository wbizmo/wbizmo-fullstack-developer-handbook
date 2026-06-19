# Lesson 02: Installing Node.js and npm

## Learning Objectives

- Install Node.js.
- Verify installation.
- Understand npm.
- Create a project.
- Understand package.json.

## Installing Node.js

Download:

https://nodejs.org

Install LTS version.

## Verify Installation

Check Node:

    node --version

Check npm:

    npm --version

## What Is npm?

npm means:

    Node Package Manager

It manages:

- Libraries
- Dependencies
- Scripts

## Create Project

    mkdir my-app

    cd my-app

Initialize:

    npm init -y

Creates:

    package.json

## What Is package.json?

Project metadata.

Contains:

- Name
- Version
- Scripts
- Dependencies

Example:

    {
      "name": "my-app",
      "version": "1.0.0"
    }

## Installing Packages

Example:

    npm install chalk

Development package:

    npm install -D typescript

## package-lock.json

Locks dependency versions.

Commit this file.

## node_modules

Contains installed packages.

Do not manually edit it.

## Hands-On Exercise

Create a Node.js project.

Initialize npm.

Install:

    chalk

## Mini Challenge

Create:

    package.json

with:

- custom name
- version
- description

## Summary

npm manages dependencies.

package.json defines projects.

Node.js projects usually begin with npm init.

## References

https://docs.npmjs.com

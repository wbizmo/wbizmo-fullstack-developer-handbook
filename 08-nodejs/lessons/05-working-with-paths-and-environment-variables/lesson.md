# Lesson 05: Working With Paths And Environment Variables

## Learning Objectives

By the end of this lesson, you should be able to:

- Use the path module.
- Build safe file paths.
- Understand environment variables.
- Access process.env.
- Use .env files.
- Protect secrets properly.

## Why Paths Matter

Bad:

    "./data/users.json"

May behave differently across systems.

Use path instead.

## Import Path Module

    import path from "node:path";

## Join Paths

Example:

    const filePath =
      path.join(
        "data",
        "users.json"
      );

Output:

    data/users.json

Works across operating systems.

## Absolute Paths

Example:

    console.log(
      process.cwd()
    );

Returns current project directory.

## Resolve Paths

    path.resolve(
      "data",
      "users.json"
    );

Creates absolute path.

## What Are Environment Variables?

Environment variables store configuration outside code.

Examples:

- Database URLs
- API keys
- Ports
- Secret tokens

## Accessing Variables

Example:

    console.log(
      process.env.PORT
    );

## Why Not Hardcode Secrets?

Bad:

    const apiKey =
      "secret-key";

If committed:

- Exposed publicly
- Security risk

## Using dotenv

Install:

    npm install dotenv

Create:

    .env

Example:

    PORT=3000
    APP_NAME=Demo

Load:

    import "dotenv/config";

Access:

    process.env.PORT

## Example

.env

    DB_HOST=localhost
    DB_PORT=5432

app.js

    import "dotenv/config";

    console.log(
      process.env.DB_HOST
    );

## Real Project Example

SyncGrid:

    DATABASE_URL

VaultBox:

    JWT_SECRET

inFlowForge:

    REDIS_URL

All stored in environment variables.

## Mini Project

Create:

    config.js

Export:

- PORT
- APP_NAME

Read from:

    process.env

## Common Beginner Mistakes

### Mistake 1

Committing .env.

### Mistake 2

Hardcoding secrets.

### Mistake 3

Not validating environment variables.

### Mistake 4

Using string paths everywhere.

## Exercises

1. Install dotenv.
2. Create .env.
3. Read environment variables.
4. Create config.js.
5. Use path.join().
6. Use path.resolve().

## Summary

Path utilities create reliable file paths.

Environment variables separate configuration from code.

Secrets belong in .env files.

## References

https://nodejs.org/api/path.html

https://nodejs.org/api/process.html

https://www.npmjs.com/package/dotenv

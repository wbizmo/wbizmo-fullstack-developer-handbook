# Lesson 08: Node.js Best Practices

## Learning Objectives

By the end of this lesson, you should be able to:

- Structure Node.js projects.
- Use environment variables.
- Handle errors.
- Avoid committing secrets.
- Use npm scripts.
- Understand production basics.

## Project Structure

Small project:

    src/
      index.js
      config.js
      utils.js

Larger project:

    src/
      controllers/
      services/
      routes/
      models/
      utils/
      config/
      index.js

## Use npm Scripts

package.json:

    {
      "scripts": {
        "start": "node src/index.js",
        "dev": "node --watch src/index.js"
      }
    }

Run:

    npm run dev

## Use Environment Variables

Bad:

    const secret = "super-secret";

Good:

    process.env.JWT_SECRET

## Use .gitignore

Example:

    node_modules
    .env
    dist
    coverage

## Error Handling

Always handle errors.

Example:

    try {
      await riskyTask();
    } catch (error) {
      console.error(error.message);
    }

## Validate Input

Never trust user input.

Examples:

- Request bodies
- CLI arguments
- Environment variables
- API responses

## Keep Logic Organized

Bad:

Everything inside index.js.

Good:

- Routes handle HTTP.
- Services handle business logic.
- Utils handle reusable helpers.
- Config handles environment settings.

## Use Linting And Formatting

Common tools:

- ESLint
- Prettier
- Biome

## Production Basics

Production apps should have:

- Logging
- Error handling
- Environment variables
- Security headers
- Rate limiting
- Health checks
- Monitoring

## Common Beginner Mistakes

- Committing .env.
- Putting all code in one file.
- Ignoring errors.
- Hardcoding secrets.
- Not using package scripts.
- Not documenting setup.

## Exercises

1. Create a clean folder structure.
2. Add npm scripts.
3. Create .gitignore.
4. Create config.js.
5. Read PORT from environment.
6. Add try...catch around async code.
7. Write README setup steps.

## Summary

Good Node.js code is organized, secure, configurable, and documented.

Best practices matter more as projects grow.

## References

https://nodejs.org/en/learn

https://docs.npmjs.com

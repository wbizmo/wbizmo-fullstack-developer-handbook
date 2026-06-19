# Lesson 08 Answers

1. Maintainability.
2. Repeatable commands.
3. Config and secrets outside code.
4. No.
5. Prevents files from being committed.
6. Prevent crashes and improve debugging.
7. User input can be invalid or unsafe.
8. Business logic.
9. ESLint, Prettier, Biome.
10. Logging, monitoring, security, health checks.

## Exercise Solution

Example structure:

    src/
      config/
        app.js
      services/
        notes.service.js
      utils/
        logger.js
      index.js

package.json scripts:

    {
      "scripts": {
        "start": "node src/index.js",
        "dev": "node --watch src/index.js"
      }
    }

.gitignore:

    node_modules
    .env
    dist
    coverage

config/app.js:

    import "dotenv/config";

    export const config = {
      port: process.env.PORT || 3000
    };

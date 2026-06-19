# Lesson 05 Answers

1. path.
2. Safe cross-platform paths.
3. Creates absolute paths.
4. Environment variables.
5. Environment variable loader.
6. Configuration management.
7. No.
8. No.
9. Current working directory.
10. Security and flexibility.

## Mini Project Solution

config.js

    import "dotenv/config";

    export const config = {
      port:
        process.env.PORT ||
        3000,

      appName:
        process.env.APP_NAME ||
        "Demo App"
    };

index.js

    import { config }
      from "./config.js";

    console.log(config);

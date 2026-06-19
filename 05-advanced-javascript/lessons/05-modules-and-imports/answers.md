# Lesson 05 Answers

1. Modules split code into reusable files.
2. An export imported by its specific name.
3. The main export from a file.
4. import { name } from "./file.js";
5. import name from "./file.js";
6. It enables module syntax in browser scripts.
7. They improve organization, reuse, and maintenance.
8. Yes.
9. Yes.
10. Forgetting type="module" or mixing imports incorrectly.

## Exercise Solution

index.html:

    <!DOCTYPE html>
    <html lang="en">
      <head>
        <meta charset="UTF-8">
        <title>Modules</title>
      </head>
      <body>
        <script type="module" src="app.js"></script>
      </body>
    </html>

math.js:

    export function add(a, b) {
      return a + b;
    }

    export function subtract(a, b) {
      return a - b;
    }

logger.js:

    export default function log(message) {
      console.log(message);
    }

app.js:

    import { add, subtract } from "./math.js";
    import log from "./logger.js";

    log(add(2, 3));
    log(subtract(10, 4));

# Lesson 05: Modules and Imports

## Learning Objectives

By the end of this lesson, you should understand why modules exist, how to export code, how to import code, default exports, named exports, and why modular code is easier to maintain.

## Why Modules Exist

Large applications should not keep all code in one file.

Modules help split code into reusable files.

Benefits:

- Better organization
- Reuse
- Easier testing
- Easier maintenance
- Cleaner architecture

## Named Export

math.js:

    export function add(a, b) {
      return a + b;
    }

Import:

    import { add } from "./math.js";

## Multiple Named Exports

    export function add(a, b) {
      return a + b;
    }

    export function subtract(a, b) {
      return a - b;
    }

Import:

    import { add, subtract } from "./math.js";

## Default Export

logger.js:

    export default function log(message) {
      console.log(message);
    }

Import:

    import log from "./logger.js";

## Renaming Imports

    import { add as sum } from "./math.js";

## Browser Modules

HTML:

    <script type="module" src="app.js"></script>

type="module" allows import and export in browser JavaScript.

## Common File Structure

    project/
      index.html
      app.js
      math.js
      logger.js

## Common Mistakes

- Forgetting type="module".
- Forgetting file extension in browser imports.
- Mixing default and named imports incorrectly.
- Creating circular dependencies.
- Making too many tiny files too early.

## Exercises

1. Create math.js.
2. Export add and subtract.
3. Import them into app.js.
4. Create logger.js with default export.
5. Import logger into app.js.
6. Use script type module in HTML.

## Summary

Modules help split code into reusable files.

Named exports export multiple values.

Default exports export one main value.

Modules are essential in modern JavaScript and React.

## References

- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export

# Lesson 03: Modules and Imports

## Learning Objectives

- Understand modules.
- Create modules.
- Export values.
- Import values.
- Understand code organization.

## What Is A Module?

A module is a file that contains reusable code.

Example:

    math.js

Contains:

    add()
    subtract()

Other files can use them.

## Why Modules Matter

Benefits:

- Reusability
- Maintainability
- Separation of concerns
- Cleaner projects

## Exporting Functions

math.js

    function add(a, b) {
      return a + b;
    }

    export { add };

## Importing Functions

app.js

    import { add } from "./math.js";

    console.log(add(2, 3));

## Export Default

math.js

    export default function add(a, b) {
      return a + b;
    }

Import:

    import add from "./math.js";

## Multiple Exports

utils.js

    export const APP_NAME = "Demo";

    export function greet() {
      console.log("Hello");
    }

Import:

    import {
      APP_NAME,
      greet
    } from "./utils.js";

## Project Structure

Bad:

    everything.js

Good:

    src/
      services/
      utils/
      models/
      controllers/

## Hands-On Exercise

Create:

    math.js

Add:

    add()
    subtract()

Import into:

    app.js

## Mini Challenge

Create:

    profile.js

Export:

- name
- location
- skill

Import into:

    index.js

Print values.

## Summary

Modules help organize code.

Exports share code.

Imports use code.

## References

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

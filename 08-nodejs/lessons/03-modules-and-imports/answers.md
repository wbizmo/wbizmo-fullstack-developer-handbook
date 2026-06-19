# Lesson 03 Answers

1. Reusable code file.
2. Better organization.
3. Shares code.
4. Uses exported code.
5. Default export.
6. Yes.
7. Maintainability.
8. Keeping responsibilities separate.
9. .js
10. It becomes difficult to maintain.

## Hands-On Exercise Solution

math.js

    export function add(a, b) {
      return a + b;
    }

    export function subtract(a, b) {
      return a - b;
    }

app.js

    import {
      add,
      subtract
    } from "./math.js";

    console.log(add(5, 3));
    console.log(subtract(5, 3));

## Mini Challenge Solution

profile.js

    export const name = "Williams";
    export const location = "Nigeria";
    export const skill = "TypeScript";

index.js

    import {
      name,
      location,
      skill
    } from "./profile.js";

    console.log(name);
    console.log(location);
    console.log(skill);

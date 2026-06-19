# Lesson 03: Conditionals and Comparisons

## Learning Objectives

By the end of this lesson, you should be able to:

- Use comparison operators.
- Understand if, else if, and else.
- Use logical operators.
- Understand truthy and falsy values.
- Write simple decision-making programs.

## What Are Conditionals?

Conditionals allow programs to make decisions.

Example:

    If the user is logged in, show dashboard.
    Otherwise, show login page.

JavaScript uses if statements for decisions.

## if Statement

    const age = 18;

    if (age >= 18) {
      console.log("You can vote");
    }

The code inside the block runs only if the condition is true.

## else Statement

    const age = 15;

    if (age >= 18) {
      console.log("Adult");
    } else {
      console.log("Minor");
    }

else runs when the if condition is false.

## else if

    const score = 75;

    if (score >= 90) {
      console.log("Excellent");
    } else if (score >= 70) {
      console.log("Good");
    } else {
      console.log("Keep practicing");
    }

## Comparison Operators

Equal value:

    ==

Strict equal:

    ===

Not equal:

    !=

Strict not equal:

    !==

Greater than:

    >

Less than:

    <

Greater than or equal:

    >=

Less than or equal:

    <=

## Strict Equality

Prefer:

    ===

over:

    ==

Example:

    5 === "5"

This is false because one value is a number and the other is a string.

## Logical Operators

AND:

    &&

OR:

    ||

NOT:

    !

Example:

    const isLoggedIn = true;
    const isAdmin = false;

    if (isLoggedIn && isAdmin) {
      console.log("Admin dashboard");
    }

## Truthy and Falsy

Some values behave like false in conditions.

Falsy values include:

- false
- 0
- ""
- null
- undefined
- NaN

Most other values are truthy.

Example:

    const username = "";

    if (username) {
      console.log("Has username");
    } else {
      console.log("No username");
    }

## Common Beginner Mistakes

- Using = instead of === in conditions.
- Forgetting curly braces.
- Writing impossible conditions.
- Confusing && and ||.
- Not understanding truthy and falsy.
- Using == instead of ===.

## Exercises

1. Write a condition that checks if age is 18 or above.
2. Write a condition that checks if a user is logged in.
3. Write a grading system using if, else if, and else.
4. Check if a password length is at least 8.
5. Use && to check if a user is logged in and verified.
6. Use || to check if a user is admin or owner.
7. Use ! to reverse a boolean.

## Summary

Conditionals allow programs to make decisions.

Comparisons evaluate relationships between values.

Logical operators combine conditions.

Most real applications depend heavily on conditionals.

## References

- https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/conditionals
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_equality
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND

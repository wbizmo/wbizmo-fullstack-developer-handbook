# Lesson 02: Variables, Data Types and Operators

## Learning Objectives

By the end of this lesson, you should be able to:

- Create variables with let and const.
- Understand why var is older and less preferred.
- Understand strings, numbers, booleans, null, and undefined.
- Use arithmetic operators.
- Use assignment operators.
- Use basic string concatenation and template literals.

## What Is A Variable?

A variable stores a value.

Example:

    let name = "Williams";

The variable name stores the value Williams.

## let

Use let when a value may change.

    let score = 0;

    score = 10;

## const

Use const when a value should not be reassigned.

    const country = "Nigeria";

This does not mean the value is deeply immutable in every situation, but for beginners, remember:

    const means do not reassign this variable.

## var

var is older JavaScript syntax.

    var age = 20;

Modern JavaScript usually prefers let and const.

## Strings

A string is text.

Examples:

    const name = "Ada";
    const city = 'Lagos';

## Numbers

Numbers can be integers or decimals.

Examples:

    const age = 25;
    const price = 19.99;

## Booleans

A boolean is true or false.

Examples:

    const isLoggedIn = true;
    const hasPaid = false;

## null

null means intentionally empty.

    const selectedUser = null;

## undefined

undefined means a value has not been assigned.

    let email;

    console.log(email);

## typeof

typeof checks the type of a value.

    console.log(typeof "Hello");
    console.log(typeof 42);
    console.log(typeof true);

## Arithmetic Operators

Addition:

    const total = 5 + 3;

Subtraction:

    const result = 10 - 4;

Multiplication:

    const price = 5 * 2;

Division:

    const share = 20 / 4;

Remainder:

    const remainder = 10 % 3;

## Assignment Operators

    let count = 0;

    count = count + 1;
    count += 1;
    count -= 1;
    count *= 2;
    count /= 2;

## String Concatenation

    const firstName = "Ada";
    const lastName = "Lovelace";

    const fullName = firstName + " " + lastName;

## Template Literals

Template literals use backticks.

    const name = "Williams";
    const message = `Hello, ${name}`;

Template literals are useful for combining text and variables.

## Common Beginner Mistakes

- Using const for values that need reassignment.
- Using let when const would be better.
- Forgetting quotes around strings.
- Confusing number 5 with string "5".
- Expecting undefined and null to mean exactly the same thing.

## Exercises

1. Create a variable for your name.
2. Create a variable for your age.
3. Create a boolean called isLearning.
4. Create two numbers and add them.
5. Create two strings and combine them.
6. Use typeof on three values.
7. Use a template literal to create a greeting.

## Summary

Variables store values.

let is used for values that can change.

const is used for values that should not be reassigned.

JavaScript has different data types such as strings, numbers, booleans, null, and undefined.

Operators allow you to calculate, assign, and combine values.

## References

- https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Variables
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_operators

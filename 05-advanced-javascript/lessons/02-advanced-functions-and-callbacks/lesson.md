# Lesson 02: Advanced Functions and Callbacks

## Learning Objectives

By the end of this lesson, you should understand first-class functions, callbacks, higher-order functions, anonymous functions, arrow functions, and function composition basics.

## First-Class Functions

JavaScript treats functions like values.

You can:

- Store functions in variables
- Pass functions as arguments
- Return functions from functions

Example:

    const greet = function () {
      console.log("Hello");
    };

    greet();

## Callback Functions

A callback is a function passed into another function.

    function runTask(callback) {
      callback();
    }

    runTask(function () {
      console.log("Task complete");
    });

## Higher-Order Functions

A higher-order function accepts a function or returns a function.

    function repeat(times, callback) {
      for (let i = 0; i < times; i++) {
        callback(i);
      }
    }

    repeat(3, function (index) {
      console.log(index);
    });

## Arrow Functions

    const add = (a, b) => {
      return a + b;
    };

Short form:

    const add = (a, b) => a + b;

## Anonymous Functions

An anonymous function has no name.

    setTimeout(function () {
      console.log("Done");
    }, 1000);

## Functions Returning Functions

    function createMultiplier(multiplier) {
      return function (number) {
        return number * multiplier;
      };
    }

    const double = createMultiplier(2);

    console.log(double(5));

## Common Use Cases

Callbacks are common in:

- Events
- Array methods
- Timers
- API operations
- Custom reusable functions

## Exercises

1. Store a function in a variable.
2. Pass a function into another function.
3. Create a repeat function that runs a callback multiple times.
4. Create a multiplier function that returns another function.
5. Rewrite a normal function as an arrow function.

## Summary

Functions are values in JavaScript.

Callbacks allow flexible behavior.

Higher-order functions power many advanced JavaScript patterns.

## References

- https://developer.mozilla.org/en-US/docs/Glossary/First-class_Function
- https://developer.mozilla.org/en-US/docs/Glossary/Callback_function
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions

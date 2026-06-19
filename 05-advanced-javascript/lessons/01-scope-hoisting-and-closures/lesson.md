# Lesson 01: Scope, Hoisting and Closures

## Learning Objectives

By the end of this lesson, you should understand scope, block scope, function scope, global scope, hoisting, lexical scope, and closures.

## Scope

Scope controls where variables can be accessed.

Global scope:

    const appName = "Handbook";

    console.log(appName);

Block scope:

    if (true) {
      const message = "Inside block";
      console.log(message);
    }

Function scope:

    function greet() {
      const name = "Ada";
      console.log(name);
    }

Variables created inside a function usually cannot be accessed outside that function.

## let and const

let and const are block-scoped.

    if (true) {
      let score = 10;
      const name = "Ada";
    }

score and name are not available outside the block.

## var

var is function-scoped and behaves differently.

Modern JavaScript usually prefers let and const.

## Hoisting

Hoisting means JavaScript processes declarations before code executes.

Function declarations can often be called before they are written:

    sayHello();

    function sayHello() {
      console.log("Hello");
    }

Variables declared with let and const are hoisted but cannot be safely accessed before declaration.

## Lexical Scope

Lexical scope means inner functions can access variables from their outer scope.

    function outer() {
      const message = "Hello";

      function inner() {
        console.log(message);
      }

      inner();
    }

## Closures

A closure happens when a function remembers variables from its outer scope even after the outer function has finished running.

    function createCounter() {
      let count = 0;

      return function () {
        count += 1;
        return count;
      };
    }

    const counter = createCounter();

    console.log(counter());
    console.log(counter());

Closures are useful for private state, factories, and advanced patterns.

## Exercises

1. Create a global variable and access it inside a function.
2. Create a block-scoped variable and try to access it outside the block.
3. Write a function that returns another function.
4. Create a counter using closure.
5. Explain why closures are useful.

## Summary

Scope controls access.

Hoisting affects declaration behavior.

Closures allow functions to remember outer variables.

## References

- https://developer.mozilla.org/en-US/docs/Glossary/Scope
- https://developer.mozilla.org/en-US/docs/Glossary/Hoisting
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures

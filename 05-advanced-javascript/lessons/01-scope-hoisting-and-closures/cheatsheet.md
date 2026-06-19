# Lesson 01 Cheatsheet

Global scope:
    Available everywhere.

Block scope:
    Inside curly braces.

Function scope:
    Inside function.

let and const:
    Block-scoped.

Closure:

    function outer() {
      let value = 0;

      return function inner() {
        value += 1;
        return value;
      };
    }

Key takeaway:
    Closures allow functions to remember outer variables.

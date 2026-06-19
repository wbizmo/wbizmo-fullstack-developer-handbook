# Lesson 02 Cheatsheet

Function value:

    const greet = function () {};

Callback:

    function run(callback) {
      callback();
    }

Arrow:

    const add = (a, b) => a + b;

Higher-order function:
    Accepts or returns a function.

Function factory:

    function createMultiplier(x) {
      return (n) => n * x;
    }

# Lesson 02 Answers

1. A function treated like a value.
2. A function passed into another function.
3. A function that accepts or returns a function.
4. A function without a name.
5. A shorter function syntax using =>.
6. Yes.
7. Events, array methods, timers, and APIs.
8. const add = (a, b) => a + b;
9. A callback function and delay.
10. They allow custom behavior to be passed into reusable code.

## Exercise Solution

    const sayHello = function () {
      console.log("Hello");
    };

    function run(callback) {
      callback();
    }

    run(sayHello);

    function repeat(times, callback) {
      for (let i = 0; i < times; i++) {
        callback(i);
      }
    }

    repeat(3, (index) => {
      console.log(index);
    });

    function createMultiplier(multiplier) {
      return (number) => number * multiplier;
    }

    const triple = createMultiplier(3);
    console.log(triple(10));

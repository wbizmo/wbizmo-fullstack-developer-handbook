# Lesson 01 Answers

1. Scope controls where variables can be accessed.
2. Global scope is accessible throughout the program.
3. Block scope exists inside curly braces.
4. Function scope exists inside a function.
5. Yes.
6. Hoisting is JavaScript's behavior of processing declarations before execution.
7. Usually yes.
8. Lexical scope means inner functions can access variables from outer scopes.
9. A closure is a function that remembers variables from its outer scope.
10. Closures are useful for private state and reusable function factories.

## Exercise Solution

    const appName = "Handbook";

    function printAppName() {
      console.log(appName);
    }

    printAppName();

    if (true) {
      const blockMessage = "Inside block";
      console.log(blockMessage);
    }

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

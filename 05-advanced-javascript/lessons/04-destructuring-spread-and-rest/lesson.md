# Lesson 04: Destructuring, Spread and Rest

## Learning Objectives

By the end of this lesson, you should understand array destructuring, object destructuring, spread syntax, rest parameters, and common use cases.

## Array Destructuring

Destructuring extracts values from arrays.

    const colors = ["red", "green", "blue"];

    const [first, second] = colors;

    console.log(first);
    console.log(second);

## Object Destructuring

Extract values from objects.

    const user = {
      name: "Ada",
      age: 25
    };

    const { name, age } = user;

## Renaming Variables

    const { name: userName } = user;

## Default Values

    const { role = "user" } = user;

## Spread With Arrays

Spread copies or combines arrays.

    const frontend = ["HTML", "CSS"];
    const backend = ["Node.js"];

    const stack = [...frontend, ...backend];

## Spread With Objects

    const user = {
      name: "Ada"
    };

    const updatedUser = {
      ...user,
      role: "Developer"
    };

## Rest Parameters

Rest gathers remaining arguments.

    function sum(...numbers) {
      return numbers.reduce((total, number) => total + number, 0);
    }

## Common Use Cases

- Copying arrays
- Copying objects
- Combining data
- Extracting values from API responses
- Function parameters
- React props later

## Exercises

1. Destructure first and second item from an array.
2. Destructure name and email from a user object.
3. Rename an object property during destructuring.
4. Combine two arrays with spread.
5. Copy an object and add a new property.
6. Create a function using rest parameters.

## Summary

Destructuring extracts values.

Spread expands arrays and objects.

Rest gathers values.

These features make modern JavaScript cleaner.

## References

- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters

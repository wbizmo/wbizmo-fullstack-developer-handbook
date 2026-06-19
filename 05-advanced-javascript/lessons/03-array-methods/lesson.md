# Lesson 03: Array Methods

## Learning Objectives

By the end of this lesson, you should understand forEach, map, filter, find, some, every, reduce, includes, and sort basics.

## Why Array Methods Matter

Real applications often work with lists.

Examples:

- Users
- Products
- Orders
- Transactions
- Posts
- Notifications

Array methods help transform, search, filter, and summarize lists.

## forEach

Runs a function for each item.

    const names = ["Ada", "Tunde", "Williams"];

    names.forEach((name) => {
      console.log(name);
    });

## map

Creates a new array by transforming each item.

    const numbers = [1, 2, 3];

    const doubled = numbers.map((number) => number * 2);

## filter

Creates a new array with items that pass a condition.

    const scores = [40, 70, 90];

    const passed = scores.filter((score) => score >= 50);

## find

Returns the first item that matches.

    const users = [
      { id: 1, name: "Ada" },
      { id: 2, name: "Tunde" }
    ];

    const user = users.find((item) => item.id === 2);

## some

Checks if at least one item matches.

    const hasHighScore = scores.some((score) => score > 80);

## every

Checks if all items match.

    const allPassed = scores.every((score) => score >= 50);

## reduce

Reduces an array into one value.

    const total = [10, 20, 30].reduce((sum, number) => {
      return sum + number;
    }, 0);

## includes

Checks if an array contains a value.

    const roles = ["admin", "user"];

    console.log(roles.includes("admin"));

## sort

Sorts an array.

    const numbers = [3, 1, 2];

    numbers.sort((a, b) => a - b);

## Common Mistakes

- Using map when forEach is enough.
- Forgetting map returns a new array.
- Forgetting filter returns an array.
- Forgetting find returns one item or undefined.
- Mutating arrays accidentally with sort.
- Making reduce too complex too early.

## Exercises

1. Use forEach to print names.
2. Use map to double numbers.
3. Use filter to get adults.
4. Use find to get a user by id.
5. Use some to check if any item is expensive.
6. Use every to check if all users are active.
7. Use reduce to calculate total price.
8. Use includes to check a role.
9. Sort numbers from low to high.

## Summary

Array methods make JavaScript powerful for working with lists.

They are essential in frontend, backend, APIs, dashboards, and data-heavy applications.

## References

- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array

# Lesson 03 Answers

1. Runs a function for each item.
2. A new transformed array.
3. A new filtered array.
4. The first matching item or undefined.
5. Whether at least one item matches.
6. Whether all items match.
7. Reduces an array into one value.
8. Checks whether a value exists.
9. Sorts an array.
10. reduce.

## Exercise Solution

    const names = ["Ada", "Tunde", "Williams"];

    names.forEach((name) => console.log(name));

    const numbers = [1, 2, 3];
    const doubled = numbers.map((number) => number * 2);

    const users = [
      { id: 1, name: "Ada", age: 22, active: true },
      { id: 2, name: "Tunde", age: 16, active: true },
      { id: 3, name: "Williams", age: 20, active: false }
    ];

    const adults = users.filter((user) => user.age >= 18);
    const selectedUser = users.find((user) => user.id === 2);
    const allActive = users.every((user) => user.active);
    const someActive = users.some((user) => user.active);

    const prices = [100, 200, 300];
    const total = prices.reduce((sum, price) => sum + price, 0);

    const roles = ["admin", "user"];
    const isAdmin = roles.includes("admin");

    const sorted = [3, 1, 2].sort((a, b) => a - b);

    console.log(doubled, adults, selectedUser, allActive, someActive, total, isAdmin, sorted);

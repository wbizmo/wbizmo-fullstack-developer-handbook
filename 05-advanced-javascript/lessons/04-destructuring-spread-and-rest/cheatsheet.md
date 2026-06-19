# Lesson 04 Cheatsheet

Array destructuring:

    const [first, second] = items;

Object destructuring:

    const { name, email } = user;

Rename:

    const { name: userName } = user;

Default:

    const { role = "user" } = user;

Array spread:

    const copy = [...items];

Object spread:

    const copy = { ...user };

Rest:

    function sum(...numbers) {}

Key takeaway:
    Destructuring, spread, and rest simplify data handling.

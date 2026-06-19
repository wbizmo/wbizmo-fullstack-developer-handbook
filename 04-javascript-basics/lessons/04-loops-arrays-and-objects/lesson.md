# Lesson 04: Loops, Arrays and Objects

## Learning Objectives

By the end of this lesson, you should be able to:

- Understand arrays.
- Access array items.
- Understand objects.
- Access object properties.
- Use for loops.
- Use for...of loops.
- Understand why loops are useful.

## What Is An Array?

An array stores multiple values in one variable.

Example:

    const languages = ["HTML", "CSS", "JavaScript"];

Arrays are useful for lists.

Examples:

- Users
- Products
- Posts
- Scores
- Tasks

## Accessing Array Items

Array indexes start at 0.

    const languages = ["HTML", "CSS", "JavaScript"];

    console.log(languages[0]);
    console.log(languages[1]);
    console.log(languages[2]);

Output:

    HTML
    CSS
    JavaScript

## Array Length

    console.log(languages.length);

This gives the number of items.

## Adding To Arrays

    const tasks = [];

    tasks.push("Learn HTML");
    tasks.push("Learn CSS");

push adds an item to the end.

## What Is An Object?

An object stores related data using key-value pairs.

Example:

    const user = {
      name: "Ada",
      age: 25,
      isDeveloper: true
    };

## Accessing Object Properties

Dot notation:

    console.log(user.name);

Bracket notation:

    console.log(user["age"]);

## Arrays Of Objects

Real applications often use arrays of objects.

Example:

    const users = [
      {
        name: "Ada",
        role: "Frontend Developer"
      },
      {
        name: "Tunde",
        role: "Backend Developer"
      }
    ];

## What Is A Loop?

A loop repeats code.

Without a loop:

    console.log("Hello");
    console.log("Hello");
    console.log("Hello");

With a loop:

    for (let i = 0; i < 3; i++) {
      console.log("Hello");
    }

## for Loop

    for (let i = 0; i < 5; i++) {
      console.log(i);
    }

Parts:

    let i = 0

starting point.

    i < 5

condition.

    i++

update after each loop.

## Looping Through Arrays

    const languages = ["HTML", "CSS", "JavaScript"];

    for (let i = 0; i < languages.length; i++) {
      console.log(languages[i]);
    }

## for...of Loop

for...of is simpler for arrays.

    for (const language of languages) {
      console.log(language);
    }

## Common Beginner Mistakes

- Forgetting arrays start at index 0.
- Accessing an item that does not exist.
- Creating infinite loops.
- Misspelling object property names.
- Confusing arrays and objects.
- Forgetting commas between object properties.

## Exercises

1. Create an array of five programming languages.
2. Print the first item.
3. Print the last item.
4. Add one item using push.
5. Create a user object with name, age, and email.
6. Print the user's name.
7. Loop through an array and print every item.
8. Create an array of three user objects.
9. Loop through users and print each name.

## Summary

Arrays store lists.

Objects store related key-value data.

Loops repeat code.

Arrays, objects, and loops are core parts of JavaScript programming.

## References

- https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Arrays
- https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics
- https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Looping_code

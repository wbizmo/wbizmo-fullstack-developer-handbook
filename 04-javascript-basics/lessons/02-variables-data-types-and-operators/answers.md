# Lesson 02 Answers: Variables, Data Types and Operators

1. A variable stores a value.
2. Use let when the value may change.
3. Use const when the variable should not be reassigned.
4. var is older and has behavior that can be confusing for beginners.
5. A string is text.
6. A number is a numeric value.
7. A boolean is true or false.
8. null is intentionally empty. undefined means no value has been assigned.
9. typeof checks the type of a value.
10. A template literal is a string created with backticks that can include variables.

## Exercise Solution

    const name = "Williams";
    let age = 20;
    const isLearning = true;

    const a = 10;
    const b = 5;
    const sum = a + b;

    const firstName = "Ada";
    const lastName = "Lovelace";
    const fullName = firstName + " " + lastName;

    console.log(typeof name);
    console.log(typeof age);
    console.log(typeof isLearning);

    const greeting = `Hello, my name is ${name} and I am learning JavaScript.`;

    console.log(sum);
    console.log(fullName);
    console.log(greeting);

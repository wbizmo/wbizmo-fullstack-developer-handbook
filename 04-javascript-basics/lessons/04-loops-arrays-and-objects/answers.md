# Lesson 04 Answers: Loops, Arrays and Objects

1. An array stores multiple values in one variable.
2. Arrays start from index 0.
3. length returns the number of items in an array.
4. push adds an item to the end of an array.
5. An object stores related data using key-value pairs.
6. A key-value pair is a property name and its value.
7. object.property.
8. A loop repeats code.
9. A for loop repeats code while a condition is true.
10. for...of is useful for looping through arrays.

## Exercise Solution

    const languages = ["HTML", "CSS", "JavaScript", "TypeScript", "Python"];

    console.log(languages[0]);
    console.log(languages[languages.length - 1]);

    languages.push("PHP");

    const user = {
      name: "Ada",
      age: 25,
      email: "ada@example.com"
    };

    console.log(user.name);

    for (const language of languages) {
      console.log(language);
    }

    const users = [
      {
        name: "Ada",
        role: "Frontend Developer"
      },
      {
        name: "Tunde",
        role: "Backend Developer"
      },
      {
        name: "Williams",
        role: "Full Stack Developer"
      }
    ];

    for (const currentUser of users) {
      console.log(currentUser.name);
    }

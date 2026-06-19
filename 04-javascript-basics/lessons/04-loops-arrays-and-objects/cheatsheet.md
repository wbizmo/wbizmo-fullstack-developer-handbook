# Lesson 04 Cheatsheet: Loops, Arrays and Objects

Array:

    const items = ["A", "B", "C"];

Access item:

    items[0]

Length:

    items.length

Add item:

    items.push("D");

Object:

    const user = {
      name: "Ada",
      age: 25
    };

Dot notation:

    user.name

Bracket notation:

    user["name"]

for loop:

    for (let i = 0; i < 5; i++) {
      console.log(i);
    }

Loop through array:

    for (const item of items) {
      console.log(item);
    }

Key takeaway:
    Arrays, objects, and loops help programs manage repeated and structured data.

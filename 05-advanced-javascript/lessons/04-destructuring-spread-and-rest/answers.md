# Lesson 04 Answers

1. Destructuring extracts values from arrays or objects.
2. Extracting values by position from arrays.
3. Extracting values by property name from objects.
4. const { name: userName } = user;
5. Spread expands arrays or objects.
6. const copy = [...items];
7. const copy = { ...user };
8. Rest gathers remaining values.
9. Three dots: ...
10. They make data handling cleaner and shorter.

## Exercise Solution

    const colors = ["red", "green", "blue"];
    const [first, second] = colors;

    const user = {
      name: "Ada",
      email: "ada@example.com",
      role: "admin"
    };

    const { name, email } = user;
    const { role: userRole } = user;

    const frontend = ["HTML", "CSS"];
    const backend = ["Node.js", "Express"];
    const stack = [...frontend, ...backend];

    const updatedUser = {
      ...user,
      active: true
    };

    function sum(...numbers) {
      return numbers.reduce((total, number) => total + number, 0);
    }

    console.log(first, second, name, email, userRole, stack, updatedUser, sum(1, 2, 3));

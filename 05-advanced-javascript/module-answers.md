# Advanced JavaScript Module Answers

1. Scope controls where variables can be accessed.
2. A closure is a function that remembers variables from its outer scope.
3. Hoisting is JavaScript's behavior of processing declarations before execution.
4. A callback is a function passed into another function.
5. A higher-order function accepts or returns a function.
6. map returns a new transformed array.
7. filter returns a new array containing matching items.
8. reduce turns an array into one final value.
9. Destructuring extracts values from arrays or objects.
10. Spread expands arrays or objects.
11. Rest gathers remaining values.
12. Modules split code into reusable files.
13. A named export is imported by its exported name.
14. A default export is the main export from a file.
15. Async JavaScript allows tasks to complete later without blocking everything.
16. A promise represents a future result.
17. async creates a function that returns a promise.
18. await waits for a promise to settle.
19. try...catch handles runtime errors.
20. JSON is a lightweight data format commonly used by APIs.
21. fetch sends HTTP requests.
22. response.json parses the response body as JSON.
23. To prevent crashes and handle failed requests gracefully.
24. Synchronous code runs line by line. Asynchronous code allows delayed tasks.
25. These concepts power APIs, React, Node.js, data handling, async operations, and real-world application logic.

## Module Practice Solution

    async function loadUsers() {
      try {
        const response = await fetch("https://jsonplaceholder.typicode.com/users");

        if (!response.ok) {
          throw new Error("Failed to load users");
        }

        const users = await response.json();

        const simplifiedUsers = users.map((user) => {
          return {
            id: user.id,
            name: user.name,
            email: user.email
          };
        });

        const selectedUser = simplifiedUsers.find((user) => user.id === 1);

        console.log(simplifiedUsers);
        console.log(selectedUser);
      } catch (error) {
        console.error(error.message);
      }
    }

    loadUsers();

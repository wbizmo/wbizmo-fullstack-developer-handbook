# JavaScript Basics Module Answers

1. JavaScript adds behavior, logic, and interactivity to webpages.
2. JavaScript runs in browsers and outside browsers using Node.js.
3. console.log prints information to the console.
4. A variable stores a value.
5. let can be reassigned. const should not be reassigned.
6. string, number, boolean, null, undefined, object.
7. typeof checks the type of a value.
8. A template literal is a string using backticks that can include variables.
9. An if statement runs code when a condition is true.
10. === checks value and type. == performs type conversion.
11. && means AND.
12. || means OR.
13. An array stores multiple values in one variable.
14. An object stores related key-value data.
15. A loop repeats code.
16. A function is a reusable block of code.
17. A parameter is input a function can receive.
18. return sends a value back from a function.
19. The DOM is the browser's representation of the HTML document.
20. addEventListener runs code when an event happens.

## Module Practice Solution

HTML:

    <!DOCTYPE html>
    <html lang="en">
      <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>JavaScript Basics Practice</title>
      </head>
      <body>
        <h1 id="title">Task List</h1>

        <input id="taskInput" type="text" placeholder="Enter task">
        <button id="addTaskBtn">Add Task</button>

        <ul id="taskList"></ul>

        <script src="script.js"></script>
      </body>
    </html>

JavaScript:

    const tasks = [];

    const taskInput = document.querySelector("#taskInput");
    const addTaskBtn = document.querySelector("#addTaskBtn");
    const taskList = document.querySelector("#taskList");

    function renderTasks() {
      taskList.textContent = "";

      for (const task of tasks) {
        const item = document.createElement("li");
        item.textContent = task;
        taskList.appendChild(item);
      }
    }

    addTaskBtn.addEventListener("click", () => {
      const task = taskInput.value;

      if (task === "") {
        console.log("Task cannot be empty");
        return;
      }

      tasks.push(task);
      taskInput.value = "";
      renderTasks();
    });

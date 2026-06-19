# Lesson 05 Answers: Functions, Events and DOM Basics

1. A function is a reusable block of code.
2. Functions organize logic and prevent repetition.
3. A parameter is an input a function can receive.
4. return sends a value back from a function.
5. An arrow function is a modern function syntax using =>.
6. DOM means Document Object Model.
7. document.querySelector selects an HTML element.
8. textContent reads or changes text inside an element.
9. An event is an action that happens in the browser.
10. addEventListener runs code when an event happens.

## Exercise Solution

HTML:

    <!DOCTYPE html>
    <html lang="en">
      <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Functions and DOM</title>
      </head>
      <body>
        <h1 id="title">JavaScript Practice</h1>

        <button id="btn">Click Me</button>
        <p id="message"></p>

        <form id="loginForm">
          <input id="email" type="email" placeholder="Email">
          <button type="submit">Submit</button>
        </form>

        <script src="script.js"></script>
      </body>
    </html>

JavaScript:

    function printName() {
      console.log("Williams");
    }

    function greet(name) {
      console.log(`Hello, ${name}`);
    }

    function add(a, b) {
      return a + b;
    }

    printName();
    greet("Ada");

    const result = add(2, 3);
    console.log(result);

    const button = document.querySelector("#btn");
    const message = document.querySelector("#message");

    button.addEventListener("click", () => {
      message.textContent = "Button clicked";
    });

    const form = document.querySelector("#loginForm");
    const email = document.querySelector("#email");

    form.addEventListener("submit", (event) => {
      event.preventDefault();
      console.log(email.value);
    });

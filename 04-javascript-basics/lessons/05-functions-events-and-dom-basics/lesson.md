# Lesson 05: Functions, Events and DOM Basics

## Learning Objectives

By the end of this lesson, you should be able to:

- Create functions.
- Use parameters and return values.
- Understand why functions are useful.
- Understand browser events.
- Select HTML elements with JavaScript.
- Change text content.
- Respond to button clicks.

## What Is A Function?

A function is a reusable block of code.

Example:

    function greet() {
      console.log("Hello");
    }

Call the function:

    greet();

## Why Functions Matter

Functions help you:

- Reuse code
- Organize logic
- Avoid repetition
- Break problems into smaller pieces
- Make code easier to test

## Function Parameters

Parameters allow functions to accept input.

    function greet(name) {
      console.log(`Hello, ${name}`);
    }

    greet("Ada");
    greet("Williams");

## Return Values

A function can return a value.

    function add(a, b) {
      return a + b;
    }

    const result = add(2, 3);

    console.log(result);

## Function Expression

    const greet = function () {
      console.log("Hello");
    };

## Arrow Function

    const greet = () => {
      console.log("Hello");
    };

Arrow functions are common in modern JavaScript.

## What Is The DOM?

DOM means Document Object Model.

The DOM is the browser's representation of the HTML page.

JavaScript can use the DOM to read and change webpage content.

## Selecting Elements

HTML:

    <h1 id="title">Old Title</h1>

JavaScript:

    const title = document.querySelector("#title");

## Changing Text

    title.textContent = "New Title";

## Events

Events are actions that happen in the browser.

Examples:

- click
- submit
- input
- change
- keydown
- mouseover

## Button Click Example

HTML:

    <button id="btn">Click Me</button>
    <p id="message"></p>

JavaScript:

    const button = document.querySelector("#btn");
    const message = document.querySelector("#message");

    button.addEventListener("click", () => {
      message.textContent = "Button clicked";
    });

## Form Event Example

HTML:

    <form id="loginForm">
      <input id="email" type="email">
      <button type="submit">Login</button>
    </form>

JavaScript:

    const form = document.querySelector("#loginForm");
    const email = document.querySelector("#email");

    form.addEventListener("submit", (event) => {
      event.preventDefault();
      console.log(email.value);
    });

event.preventDefault stops the form from refreshing the page immediately.

## Common Beginner Mistakes

- Forgetting to call the function.
- Forgetting return.
- Selecting an element that does not exist.
- Running JavaScript before HTML loads.
- Misspelling querySelector.
- Forgetting event.preventDefault on forms.
- Using the same ID multiple times.

## Exercises

1. Create a function that prints your name.
2. Create a function that accepts a name and prints a greeting.
3. Create a function that adds two numbers and returns the result.
4. Create an HTML button.
5. Use JavaScript to select the button.
6. Add a click event listener to the button.
7. Change a paragraph's text when the button is clicked.
8. Create a form and prevent default submission.
9. Log input value to the console.

## Summary

Functions organize reusable code.

Parameters allow functions to receive input.

Return values allow functions to produce output.

The DOM allows JavaScript to interact with HTML.

Events allow JavaScript to respond to user actions.

## References

- https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Functions
- https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model
- https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events

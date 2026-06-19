# Lesson 01: Introduction To JavaScript

## Learning Objectives

By the end of this lesson, you should be able to:

- Explain what JavaScript is.
- Understand the role of JavaScript in web development.
- Understand where JavaScript runs.
- Add JavaScript to an HTML page.
- Use console.log.
- Understand basic browser developer tools.

## What Is JavaScript?

JavaScript is a programming language used to make websites interactive.

HTML creates structure.

CSS creates visual style.

JavaScript creates behavior.

Examples of JavaScript behavior:

- Opening mobile menus
- Validating forms
- Showing alerts
- Fetching data from APIs
- Updating dashboards
- Creating sliders
- Handling button clicks
- Building full web applications

## JavaScript In The Browser

Browsers include JavaScript engines.

Examples:

- Chrome uses V8
- Firefox uses SpiderMonkey
- Safari uses JavaScriptCore

These engines read and run JavaScript code.

## JavaScript Outside The Browser

JavaScript can also run outside browsers using Node.js.

Node.js allows JavaScript to build:

- Servers
- APIs
- CLIs
- Automation scripts
- Backend applications

This module focuses on beginner JavaScript mostly in the browser.

## Adding JavaScript To HTML

You can add JavaScript using the script element.

Inline script:

    <script>
      console.log("Hello JavaScript");
    </script>

External script:

    <script src="script.js"></script>

Common best practice:

Place the script before the closing body tag.

Example:

    <!DOCTYPE html>
    <html lang="en">
      <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>JavaScript Practice</title>
      </head>
      <body>
        <h1>Hello JavaScript</h1>

        <script src="script.js"></script>
      </body>
    </html>

## Your First JavaScript File

Create:

    script.js

Add:

    console.log("Hello JavaScript");

Open the HTML file in a browser.

Open developer tools.

Check the Console tab.

## console.log

console.log prints information to the browser console.

Example:

    console.log("Learning JavaScript");

It is useful for:

- Testing code
- Debugging
- Checking values
- Understanding program flow

## Alert

alert displays a popup message.

Example:

    alert("Welcome!");

Use alert carefully. It can interrupt the user experience.

## Comments

Comments are notes inside code.

Single-line comment:

    // This is a comment

Multi-line comment:

    /*
      This is a multi-line comment.
    */

Comments help explain code.

## Common Beginner Mistakes

- Forgetting to link script.js.
- Misspelling the file name.
- Placing script before HTML elements and trying to access them too early.
- Forgetting to open the browser console.
- Confusing Java and JavaScript.
- Expecting console.log to appear on the webpage.

## Exercises

1. Create an index.html file.
2. Create a script.js file.
3. Link script.js to index.html.
4. Use console.log to print your name.
5. Use console.log to print your favorite programming language.
6. Add a comment explaining what the file does.
7. Open browser developer tools and find the console output.

## Did You Know?

JavaScript was created in only about 10 days in 1995.

## Fun Fact

JavaScript and Java are not the same language. Their names are similar mostly because of marketing history.

## Summary

JavaScript adds behavior to webpages.

It runs in browsers and can also run on servers using Node.js.

console.log helps developers inspect values and debug code.

JavaScript is essential for modern full stack development.

## References

- https://developer.mozilla.org/en-US/docs/Web/JavaScript
- https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps

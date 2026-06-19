# Lesson 05 Cheatsheet: Functions, Events and DOM Basics

Function:

    function greet() {
      console.log("Hello");
    }

Call function:

    greet();

Parameter:

    function greet(name) {
      console.log(name);
    }

Return:

    function add(a, b) {
      return a + b;
    }

Arrow function:

    const greet = () => {
      console.log("Hello");
    };

Select element:

    document.querySelector("#id");

Change text:

    element.textContent = "New text";

Click event:

    button.addEventListener("click", () => {
      console.log("Clicked");
    });

Form submit:

    form.addEventListener("submit", (event) => {
      event.preventDefault();
    });

Key takeaway:
    Functions organize code. DOM and events connect JavaScript to webpages.

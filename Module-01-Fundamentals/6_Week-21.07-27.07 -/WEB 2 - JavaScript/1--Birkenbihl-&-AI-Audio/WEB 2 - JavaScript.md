Welcome to the world of JavaScript! In this pre-class preparation, we'll lay the groundwork for understanding what JavaScript is, how it works in web browsers, and its basic syntax. This will prepare you for our live session where we'll dive deeper into making web pages interactive.

## What is JavaScript?

JavaScript is a powerful and versatile programming language primarily known as the scripting language for Web pages. But it's also used in many non-browser environments. For our purposes, we'll focus on its role in web development.

Think of a website as a house:

- **HTML (HyperText Markup Language)** is the structure of the house – the walls, roof, doors, and windows. It defines the content and its organization.
- **CSS (Cascading Style Sheets)** is the interior and exterior design – the paint colors, furniture style, and landscaping. It controls the presentation and appearance of the HTML content.
- **JavaScript (JS)** makes the house interactive and dynamic. It's like the electrical wiring, plumbing, and appliances that allow you to turn on lights, open automated doors, or have a security system that reacts to movement.

![5404442c-f84a-4351-98a8-7175cf7c43ab.png](attachment:01080819-67b2-4782-b414-0eaadb732da3:5404442c-f84a-4351-98a8-7175cf7c43ab.png)

JavaScript allows you to implement complex features on web pages. Every time you see a dynamic map, an animated graphic, a live content update, or an interactive form, JavaScript is likely involved. It runs directly in the user's web browser (client-side), which means it can respond quickly to user actions without needing to constantly communicate with a web server.

## Basic Syntax

Like any language, JavaScript has its own grammar and rules, which we call syntax. Here are some fundamental aspects:

**Statements** A JavaScript program is a sequence of statements. Each statement is an instruction for the computer to perform an action. Statements in JavaScript are typically ended with a semicolon (`;`), although it's sometimes optional due to a feature called Automatic Semicolon Insertion (ASI). However, it's good practice to include semicolons to avoid ambiguity.

```jsx
let message = "Hello, students!";
console.log(message);
```

**Comments** Comments are notes that you can add to your code. They are ignored by the JavaScript engine but are invaluable for explaining what your code does, both for yourself and for others who might read it.

There are two types of comments:

- Single-line comments: Start with `//`. Everything after `//` on that line is a comment.
    
    ```jsx
    // This is a single-line comment
    let x = 10; // This comment explains what x might be for
    ```
    
- Multi-line comments: Start with `/*` and end with `*/`. Everything between them is a comment.
    
    ```jsx
    /*
    This is a
    multi-line comment.
    It can span several lines.
    */
    let y = 20;
    ```
    

**Case Sensitivity** JavaScript is case-sensitive. This means that `myVariable`, `MyVariable`, and `myvariable` would be treated as three distinct variables. Always pay close attention to capitalization.

## Where Does JavaScript Code Go?

You can include JavaScript in your HTML documents in a few ways. You'll use Visual Studio Code (VS Code), which you're already familiar with from Python, to create and edit your HTML (`.html`) and JavaScript (`.js`) files. Typically, you'll create a project folder, open it in VS Code, and then add your files there. To see your work, you'll open the HTML file directly in your web browser.

1. **Internal JavaScript (within `<script>` tags):** You can embed JavaScript code directly within your HTML file using `<script>` tags. Typically, these are placed just before the closing `</body>` tag so that the HTML structure is loaded before the script tries to interact with it.
    
    ```jsx
    <!DOCTYPE html>
    <html>
    <head>
        <title>My First JS Page</title>
    </head>
    <body>
        <h1>Welcome!</h1>
        <p id="greeting"></p>
    
        <script>
            // JavaScript code goes here
            let studentName = "Alex";
            document.getElementById("greeting").innerHTML = "Hello, " + studentName + "!";
        </script>
    </body>
    </html>
    ```
    
2. **External JavaScript (linking to `.js` files):** This is the most common and recommended method for larger scripts. You write your JavaScript code in a separate file with a `.js` extension (e.g., `myscript.js`) and then link to it from your HTML file using the `<script>` tag with the `src` attribute.
    
    **HTML file (`index.html`):**
    
    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <title>My External JS Page</title>
    </head>
    <body>
        <h1>Content</h1>
        <p id="message"></p>
    
        <script src="myscript.js"></script>
    </body>
    </html>
    ```
    
    **JavaScript file (`myscript.js`):**
    
    ```jsx
    // Contents of myscript.js
    let visitor = "Chris";
    document.getElementById("message").innerHTML = "Greetings, " + visitor;
    ```
    
    Using external files helps keep your HTML cleaner, makes your JavaScript reusable across multiple pages, and improves site performance through browser caching.
    
3. **Inline JavaScript (in HTML attributes - use sparingly):** JavaScript can also be placed directly within HTML attributes, like `onclick` or `onmouseover`. This is generally discouraged for anything more than very simple actions because it mixes structure (HTML) with behavior (JavaScript) too closely, making the code harder to maintain.
    
    ```jsx
    <button onclick="alert('Button clicked!');">Click Me</button>
    ```
    

### Think about it

- Why is it generally better to place your `<script>` tags at the end of the `<body>` section rather than in the `<head>`?
- What are the advantages of using external JavaScript files over internal scripts?

## Variables

Variables are containers for storing data values. Think of them as named storage locations. In JavaScript, you can declare variables using `var`, `let`, or `const`.

- **`let`**: Declares a block-scoped local variable, optionally initializing it to a value. Block-scoped means the variable is only accessible within the block of code (e.g., inside an `if` statement or a `for` loop) where it's defined. This is the preferred way to declare variables that might be reassigned.
    
    ```jsx
    let age = 30;
    age = 31; // This is allowed
    ```
    
- **`const`**: Declares a block-scoped local variable, but its value cannot be reassigned after it's initialized. It's short for "constant". Use `const` for values that you know shouldn't change.
    
    ```jsx
    const birthYear = 1990;
    // birthYear = 1991; // This would cause an error
    ```
    
- **`var`**: This was the original way to declare variables in JavaScript. It has function scope or global scope, and has some quirks (like hoisting) that can lead to confusion. While you'll see it in older code, modern JavaScript development generally favors `let` and `const`.
    

**Naming Conventions**

- Variable names can contain letters, digits, underscores (`_`), and dollar signs (`$`).
- They must begin with a letter, underscore, or dollar sign. They cannot start with a number.
- Names are case-sensitive (e.g., `user` and `User` are different).
- It's common practice to use **camelCase** for variable names (e.g., `firstName`, `userProfileData`).
- Avoid using reserved keywords (like `let`, `const`, `function`, `if`, etc.) as variable names.

## Data Types

JavaScript variables can hold various types of data. JavaScript is a **dynamically typed** language, meaning you don't have to explicitly declare the type of a variable. The type is determined automatically at runtime.

Here are the basic (primitive) data types:

- **String**: Represents textual data. Strings are enclosed in single quotes (`'...'`), double quotes (`"..."`), or backticks (`...`).
    
    ```jsx
    let greeting = "Hello, world!";
    let name = 'Alice';
    let message = `Welcome, ${name}!`; // Using backticks for template literals
    ```
    
- **Number**: Represents numeric data, including integers and floating-point numbers.
    
    ```jsx
    let count = 10;
    let price = 19.99;
    ```
    
- **Boolean**: Represents a logical entity and can have two values: `true` or `false`.
    
    ```jsx
    let isActive = true;
    let isLoggedIn = false;
    ```
    
- **Null**: Represents the intentional absence of any object value. It's a special value that means "no value" or "empty".
    
    ```jsx
    let userData = null; // Explicitly set to no value
    ```
    
- **Undefined**: Represents a variable that has been declared but not yet assigned a value.
    
    ```jsx
    let city; // city is undefined
    ```
    

There's also a complex data type called **Object**, which we'll explore in more detail later. Arrays and Functions are also types of objects in JavaScript.

You can check the type of a variable using the `typeof` operator:

```jsx
let score = 100;
console.log(typeof score); // Output: "number"

let playerName = "PlayerOne";
console.log(typeof playerName); // Output: "string"
```

### Try it yourself

1. Open your web browser's developer console (see "Interacting with the Browser" section below if unsure how).
2. Declare a variable using `let` and assign it your favorite color as a string.
3. Declare another variable using `const` and assign it the current year as a number.
4. Use `console.log()` to print both variables and their types using the `typeof` operator.

## Basic Operators

Operators are special symbols used to perform operations on operands (values and variables).

**Arithmetic Operators**

- `+` (Addition)
- `-` (Subtraction)
- `*` (Multiplication)
- `/` (Division)
- `%` (Modulus - remainder of a division)
- `**` (Exponentiation)

```jsx
let x = 10;
let y = 5;
console.log(x + y); // 15
console.log(x % y); // 0 (10 divided by 5 has a remainder of 0)
console.log(2 ** 3); // 8 (2 to the power of 3)
```

**Assignment Operators**

- `=` (Assignment)
- `+=` (Addition assignment: `x += y` is `x = x + y`)
- `-=` (Subtraction assignment)
- `*=` (Multiplication assignment)
- `/=` (Division assignment)

```jsx
let total = 100;
total += 50; // total is now 150
```

**Comparison Operators** These operators compare two values and return a boolean (`true` or `false`).

- `==` (Equal to - loose equality, performs type coercion)
- `===` (Strictly equal to - checks value and type, no type coercion)
- `!=` (Not equal to - loose inequality)
- `!==` (Strictly not equal to - checks value and type)
- `>` (Greater than)
- `<` (Less than)
- `>=` (Greater than or equal to)
- `<=` (Less than or equal to)

**It is strongly recommended to use strict equality (`===`) and strict inequality (`!==`) to avoid unexpected behavior due to type coercion.**

```jsx
console.log(5 == "5");   // true (string "5" is coerced to number 5)
console.log(5 === "5");  // false (number 5 is not the same type as string "5")
console.log(10 > 5);     // true
```

**Logical Operators** Used to combine or invert boolean values.

- `&&` (Logical AND: `true` if both operands are `true`)
- `||` (Logical OR: `true` if at least one operand is `true`)
- `!` (Logical NOT: inverts the boolean value)

```jsx
let isAdult = true;
let hasTicket = false;

console.log(isAdult && hasTicket); // false
console.log(isAdult || hasTicket); // true
console.log(!hasTicket);          // true
```

### Think about it

- What would be the result of `0 == false`? What about `0 === false`? Why?
- Consider `let a = 5; let b = "10"; console.log(a + b);`. What do you expect the output to be and why?

## Interacting with the Browser

JavaScript's primary playground in web development is a modern web browser like Google Chrome or Mozilla Firefox (ensure yours is up-to-date). These browsers come with built-in **Developer Tools (DevTools)** that are essential for web development.

**How to open Developer Tools (DevTools):**

- **Chrome:** Right-click anywhere on a webpage and select "Inspect", or press `Cmd+Option+I` (on Mac).
- **Firefox:** Right-click anywhere on a webpage and select "Inspect Element", or press `Cmd+Option+I` (on Mac). Once DevTools is open, look for the **Console** tab. This is where `console.log()` messages appear and where you can type and execute JavaScript code directly.

**`console.log()`** The `console.log()` method writes a message to the browser's developer console. It's incredibly useful for debugging your code, checking variable values, and understanding the flow of execution.

**`alert()`** The `alert()` method displays a simple dialog box with a message and an OK button. It's modal, meaning it blocks further interaction with the page until the user dismisses it.

```jsx
alert("This is an alert message!");
```

While `alert()` can be useful for quick tests, it's generally not recommended for user interaction in modern web applications because it can be disruptive.

**A Glimpse into DOM Manipulation** The Document Object Model (DOM) is a programming interface for HTML documents. It represents the page so that programs can change the document structure, style, and content. JavaScript can interact with the DOM to dynamically update what the user sees.

Here's a very simple example:

```html
<p id="myParagraph">This is some text.</p>

<script>
    // Find the HTML element with the id "myParagraph"
    let paragraphElement = document.getElementById("myParagraph");
    // Change its content
    paragraphElement.innerHTML = "The text has been changed by JavaScript!";
</script>
```

We will explore DOM manipulation in much more detail in our live session and subsequent lessons.

### Try it yourself

1. Create a new HTML file named `test.html` on your computer using VS Code.
    
2. Add the following basic HTML structure:
    
    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <title>JS Test</title>
    </head>
    <body>
        <h1>JavaScript Test Page</h1>
        <script>
            console.log("Hello from the internal script!");
            alert("Page loaded!");
        </script>
    </body>
    </html>
    ```
    
3. Save the file and open it in your web browser.
    
4. Observe the alert box.
    
5. Open the developer console (e.g., right-click, Inspect, then Console tab). Do you see the message "Hello from the internal script!"?
    
6. In the console, type `2 + 2` and press Enter. What happens?
    
7. Type `let myName = "Your Name";` (replace "Your Name" with your actual name) and press Enter. Then type `console.log(myName);` and press Enter.
    

This concludes your pre-class preparation for JavaScript. By understanding these core concepts, you'll be well-equipped for our interactive session. Get ready to bring your web pages to life!

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Web-2-JavaScript-kqpyqgm7owh4hdt?mode=doc](https://gamma.app/docs/Web-2-JavaScript-kqpyqgm7owh4hdt?mode=doc)

Try not to peek before class - spoilers inside!

</aside>
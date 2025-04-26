# JavaScript Core Concepts Notes

## 1. "use strict" Mode
The `"use strict"` directive enables strict mode in JavaScript, which enforces stricter parsing and error handling. 
Example:
```javascript
// Without strict mode - will work but not recommended
x = 90;
console.log(x);

// With strict mode - will throw an error because x is not declared
"use strict";
x = 90; // Error: x is not defined
```

## 2. Hoisting
Hoisting is JavaScript's default behavior of moving declarations to the top of their scope.
```javascript
c = 90;
var c;
console.log(c); // Outputs: 90
```

## 3. Operators

### 3.1 Increment Operator
```javascript
var a = 9;
console.log(++a); // Pre-increment: outputs 10
```

### 3.2 Bitwise Operators

#### Left Shift (<<)
```javascript
var a = 8;
var b = 2;
console.log(a << b); // Output: 32
// Formula: a * (2^b)
// 8 * (2^2) = 8 * 4 = 32
```

#### Right Shift (>>)
```javascript
var a = 12;
var b = 2;
console.log(a >> b); // Output: 3
// Formula: a / (2^b)
// 12 / (2^2) = 12 / 4 = 3
```

#### Bitwise AND (&)
```javascript
var a = 8;  // 1000 in binary
var b = 2;  // 0010 in binary
console.log(a & b); // Output: 0
// 1000
// 0010
// ----
// 0000
```

#### Bitwise OR (|)
```javascript
var a = 8;  // 1000 in binary
var b = 2;  // 0010 in binary
console.log(a | b); // Output: 10
// 1000
// 0010
// ----
// 1010 (10 in decimal)
```

#### Bitwise NOT (~)
```javascript
var a = 8;
console.log(~a); // Output: -9
// Formula: -(a + 1)
```

## 4. Number Methods

### 4.1 toExponential()
Converts a number to exponential notation:
```javascript
let f = 9.656;
console.log(f.toExponential(2)); // Output: 9.66e+0
console.log(f.toExponential(4)); // Output: 9.6560e+0
```

### 4.2 toPrecision()
Formats a number to a specified length:
```javascript
let f = 9.656;
console.log(f.toPrecision()); // Returns number as string with precise decimal points
```

### 4.3 parseInt()
Converts string to integer:
- Note: "10 years" is valid for parseInt (returns 10)
- "years 10" is not valid (returns NaN)

## 5. Logical Operators
- `&&` (AND): Returns true when both conditions are true
- `||` (OR): Returns true when either condition is true
- `!` (NOT): Returns true when condition is false

## 6. Comparison Operators

### 6.1 Regular Comparisons
```javascript
5 == "5"   // true (loose equality)
5 === "5"  // false (strict equality)
6 != "5"   // true
6 !== "5"  // true
5 <= 6     // true
7 > 9      // false
```

### 6.2 Special Comparisons
```javascript
Object.is(0, 0)      // true
Object.is(+0, -0)    // false
Object.is(NaN, NaN)  // true
NaN == NaN           // false
0 == 0               // true
0 === 0              // true
+0 === -0            // true
```

## 7. Conditional (Ternary) Operator
```javascript
var a = 5;
(a == 2) ? console.log('true') : console.log('false'); // Output: false
```

## 8. Date Methods

JavaScript provides various methods to work with dates and times. Here are the commonly used Date methods:

```javascript
var d = new Date(); // Creates a new Date object with current date and time

// Get various date components
console.log(d);                // Full date and time
console.log(d.getDate());      // Day of the month (1-31)
console.log(d.getMonth());     // Month (0-11, where 0 is January)
console.log(d.getFullYear());  // Year (4 digits)
console.log(d.getHours());     // Hours (0-23)
console.log(d.getMinutes());   // Minutes (0-59)
console.log(d.getSeconds());   // Seconds (0-59)
console.log(d.getMilliseconds()); // Milliseconds (0-999)
console.log(d.getTime());      // Timestamp (milliseconds since Jan 1, 1970)
```

### Important Notes about Date Methods:
- `getMonth()` returns 0-11 (0 = January, 11 = December)
- `getDate()` returns 1-31 (day of the month)
- `getTime()` returns the number of milliseconds since January 1, 1970
- All time-related methods (getHours, getMinutes, etc.) are based on the local time zone 

## 9. Math Methods

JavaScript's Math object provides various mathematical functions and constants. Here are the commonly used Math methods:

```javascript
// Rounding Methods
console.log(Math.round(4.6));  // Output: 5 (rounds to nearest integer)
console.log(Math.ceil(4.1));   // Output: 5 (rounds up to nearest integer)
console.log(Math.floor(4.9));  // Output: 4 (rounds down to nearest integer)
console.log(Math.trunc(8.1));  // Output: 8 (removes decimal part)

// Absolute Value
console.log(Math.abs(-4.9));   // Output: 4.9 (returns absolute value)

// Random Number
console.log(Math.random());    // Output: random number between 0 and 1

// Min/Max Methods
console.log(Math.max(23, 34, 55, 88, 99, 100));  // Output: 100 (returns largest number)
console.log(Math.min(23, 34, 55, 88, 99, 100));  // Output: 23 (returns smallest number)

// Mathematical Operations
console.log(Math.sqrt(64));    // Output: 8 (square root)
console.log(Math.pow(2, 3));   // Output: 8 (2 raised to power 3)

// Constants
console.log(Math.PI);          // Output: 3.141592653589793 (value of π)
```

### Important Notes about Math Methods:
- `Math.random()` returns a random number between 0 (inclusive) and 1 (exclusive)
- `Math.round()` rounds to the nearest integer (0.5 rounds up)
- `Math.ceil()` always rounds up
- `Math.floor()` always rounds down
- `Math.trunc()` removes the decimal part without rounding
- `Math.pow(x, y)` is equivalent to x^y
- `Math.sqrt(x)` returns the square root of x
- `Math.PI` is a constant representing the ratio of a circle's circumference to its diameter

## 10. Conditional Statements

JavaScript provides several ways to make decisions in your code using conditional statements.

### 10.1 if-else if-else Statement
The if-else if-else statement allows you to execute different blocks of code based on different conditions.

```javascript
var age = 40;

if (age == 40) {
    console.log("Main Voter");
}
else if (age >= 18 && age < 60) {
    console.log("Can give vote");
}
else {
    console.log("can't give vote");
}
```

### 10.2 switch Statement
The switch statement is used to perform different actions based on different conditions. It's particularly useful when you have multiple conditions to check against a single value.

```javascript
var day = "sun";

switch(day) {
    case "mon":
        console.log("Today is Monday");
        break;
    case "tues":
        console.log("Today is Tuesday");
        break;
    case "wed":
        console.log("Today is Wednesday");
        break;
    case "thurs":
        console.log("Today is Thursday");
        break;
    case "fri":
        console.log("Today is Friday");
        break;
    case "sat":
        console.log("Today is Saturday");
        break;
    case "sun":
        console.log("Today is Sunday");
        break;
}
```

### Important Notes about Conditional Statements:
- Conditions are evaluated in order from top to bottom
- Once a condition is met, its corresponding code block is executed and the rest are skipped
- The `else` block is optional and will execute if none of the previous conditions are met
- Multiple conditions can be combined using logical operators (&&, ||)
- Conditions can be any expression that evaluates to a boolean value

### Important Notes about switch Statement:
- The `switch` expression is evaluated once
- The value of the expression is compared with the values of each `case`
- If there is a match, the associated block of code is executed
- The `break` keyword breaks out of the switch block
- Without `break`, execution will continue into the next case
- The `default` case (optional) is executed if no case matches
- Case values must be of the same type as the switch expression

## 11. Loops

JavaScript provides several types of loops to execute a block of code repeatedly.

### 11.1 for Loop
The for loop is used when you know how many times you want to execute a block of code.

```javascript
// Basic for loop
for (let i = 0; i < 5; i++) {
    console.log(i); // Output: 0, 1, 2, 3, 4
}

// Iterating through an array
const fruits = ['apple', 'banana', 'orange'];
for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
}
```

### 11.2 while Loop
The while loop is used when you want to execute a block of code as long as a condition is true.

```javascript
let i = 0;
while (i < 5) {
    console.log(i); // Output: 0, 1, 2, 3, 4
    i++;
}
```

### 11.3 do-while Loop
The do-while loop is similar to the while loop, but it executes the code block at least once before checking the condition.

```javascript
let i = 0;
do {
    console.log(i); // Output: 0, 1, 2, 3, 4
    i++;
} while (i < 5);
```

### 11.4 for...of Loop
The for...of loop is used to iterate over iterable objects like arrays, strings, etc.

```javascript
const fruits = ['apple', 'banana', 'orange'];
for (const fruit of fruits) {
    console.log(fruit);
}
```

### 11.5 for...in Loop
The for...in loop is used to iterate over the properties of an object.

```javascript
const person = {
    name: 'John',
    age: 30,
    city: 'New York'
};

for (const key in person) {
    console.log(`${key}: ${person[key]}`);
}
```

### 11.6 forEach Loop
The `forEach` loop is a method available for arrays in JavaScript. It allows you to iterate over array elements and execute a callback function for each element.

```javascript
const fruits = ['apple', 'banana', 'orange'];

fruits.forEach(function(fruit) {
    console.log(fruit); // Output: apple, banana, orange
});

// Using an arrow function with forEach
fruits.forEach(fruit => console.log(fruit));
```

### Important Notes about forEach:
- The `forEach` method does not return a new array (unlike `map`).
- It cannot be used with `break` or `continue` to control the loop.
- The callback function takes three arguments:
  1. The current element (`element`).
  2. The index of the current element (`index`).
  3. The array being traversed (`array`).

Example with all arguments:
```javascript
fruits.forEach((fruit, index, array) => {
    console.log(`Element: ${fruit}, Index: ${index}, Array: ${array}`);
});
```

### Important Notes about Loops:
- Use `break` to exit a loop completely
- Use `continue` to skip the current iteration and move to the next one
- Be careful with infinite loops (loops that never end)
- The `for...of` loop is preferred for arrays and strings
- The `for...in` loop is used for objects
- Always ensure your loop has a way to terminate

## 12. Functions

Functions are one of the fundamental building blocks in JavaScript. They allow you to define a block of code, give it a name, and then execute it whenever you need.

### 12.1 Function Declaration
```javascript
function greet(name) {
    return `Hello, ${name}!`;
}
console.log(greet('John')); // Output: Hello, John!
```

### 12.2 Function Expression
```javascript
const greet = function(name) {
    return `Hello, ${name}!`;
};
console.log(greet('John')); // Output: Hello, John!
```

### 12.3 Arrow Functions (ES6)
```javascript
const greet = (name) => {
    return `Hello, ${name}!`;
};
// Shorter version for single expression
const greet = name => `Hello, ${name}!`;
```

### 12.4 Function Parameters and Arguments
```javascript
// Default parameters
function greet(name = 'Guest') {
    return `Hello, ${name}!`;
}

// Rest parameters
function sum(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}
console.log(sum(1, 2, 3, 4)); // Output: 10
```

### 12.5 Function Scope
```javascript
let globalVar = 'I am global';

function testScope() {
    let localVar = 'I am local';
    console.log(globalVar); // Can access global variable
    console.log(localVar);  // Can access local variable
}

console.log(globalVar); // Can access global variable
// console.log(localVar); // Error: localVar is not defined
```

### 12.6 Higher-Order Functions
```javascript
// Function that takes another function as argument
function applyOperation(x, y, operation) {
    return operation(x, y);
}

const add = (a, b) => a + b;
const multiply = (a, b) => a * b;

console.log(applyOperation(5, 3, add));      // Output: 8
console.log(applyOperation(5, 3, multiply)); // Output: 15
```

### 12.7 Callback Functions
```javascript
function processData(data, callback) {
    // Process data
    const result = data.toUpperCase();
    // Call the callback function
    callback(result);
}

processData('hello', (result) => {
    console.log(result); // Output: HELLO
});
```

### 12.8 Immediately Invoked Function Expression (IIFE)
```javascript
(function() {
    console.log('This runs immediately');
})();

// With parameters
(function(name) {
    console.log(`Hello, ${name}!`);
})('John');
```

### Important Notes about Functions:
- Functions can be assigned to variables
- Functions can be passed as arguments to other functions
- Functions can return other functions
- Functions have their own scope
- Variables declared inside a function are not accessible outside
- Functions can access variables from their outer scope
- Arrow functions don't have their own `this` binding
- Function declarations are hoisted, but function expressions are not
- Default parameters must come after regular parameters
- Rest parameters must be the last parameter

## 13. Error Handling

JavaScript provides the `try...catch` statement to handle errors gracefully. It allows you to execute code and catch any errors that occur during execution.

### Syntax:
```javascript
try {
    // Code that may throw an error
} catch (error) {
    // Code to handle the error
}
```

### Example:
```javascript
try {
    console.log("This is the try block.");
    // Intentionally causing an error
    let result = 10 / 0;
    console.log(result);
} catch (error) {
    console.log("An error occurred:", error.message);
}
```

### Important Notes:
- The `try` block contains code that might throw an error.
- The `catch` block handles the error if one occurs.
- The `catch` block receives an `error` object that contains details about the error.
- The `finally` block (optional) can be used to execute code regardless of whether an error occurred or not.

### Example with `finally`:
```javascript
try {
    console.log("Trying to execute code...");
    throw new Error("Something went wrong!");
} catch (error) {
    console.log("Caught an error:", error.message);
} finally {
    console.log("This will always execute.");
}
```

## 14. Dialog Boxes

JavaScript provides three types of dialog boxes to interact with users: `alert`, `prompt`, and `confirm`.

### 14.1 `alert()`
The `alert()` method displays a simple message in a dialog box. It is often used to show information to the user.

```javascript
alert("This is an alert message!");
```

### Important Notes:
- The `alert()` dialog box only has an "OK" button.
- It pauses the execution of the script until the user closes the dialog box.

---

### 14.2 `prompt()`
The `prompt()` method displays a dialog box that asks the user for input. It returns the input as a string or `null` if the user cancels.

```javascript
let name = prompt("What is your name?");
if (name) {
    console.log(`Hello, ${name}!`);
} else {
    console.log("No name entered.");
}
```

### Important Notes:
- The first argument is the message to display.
- The second argument (optional) is the default value for the input field.
- If the user clicks "Cancel," the method returns `null`.

---

### 14.3 `confirm()`
The `confirm()` method displays a dialog box with a message and "OK" and "Cancel" buttons. It returns `true` if the user clicks "OK" and `false` if the user clicks "Cancel."

```javascript
let isConfirmed = confirm("Do you want to proceed?");
if (isConfirmed) {
    console.log("User confirmed.");
} else {
    console.log("User canceled.");
}
```

### Important Notes:
- Use `confirm()` to ask the user for confirmation before performing an action.
- It pauses the execution of the script until the user responds.

---

### Example Using All Three:
```javascript
alert("Welcome to the website!");

let name = prompt("What is your name?", "Guest");
if (name) {
    let isConfirmed = confirm(`Is your name ${name}?`);
    if (isConfirmed) {
        console.log(`Welcome, ${name}!`);
    } else {
        console.log("Name not confirmed.");
    }
} else {
    console.log("No name entered.");
}
```

## 15. Window Dimensions

JavaScript provides properties to get the height and width of the browser window.

### 15.1 `window.innerWidth` and `window.innerHeight`
These properties return the width and height of the browser's viewport (the visible area of the web page).

```javascript
console.log("Window Width:", window.innerWidth);   // Example: 1024
console.log("Window Height:", window.innerHeight); // Example: 768
```

### 15.2 `document.documentElement.clientWidth` and `document.documentElement.clientHeight`
These properties return the width and height of the viewport, excluding scrollbars.

```javascript
console.log("Viewport Width:", document.documentElement.clientWidth);
console.log("Viewport Height:", document.documentElement.clientHeight);
```

### 15.3 `window.outerWidth` and `window.outerHeight`
These properties return the width and height of the browser window, including toolbars and scrollbars.

```javascript
console.log("Outer Window Width:", window.outerWidth);
console.log("Outer Window Height:", window.outerHeight);
```

### Example:
```javascript
console.log("Window Dimensions:");
console.log("Inner Width:", window.innerWidth);
console.log("Inner Height:", window.innerHeight);
console.log("Outer Width:", window.outerWidth);
console.log("Outer Height:", window.outerHeight);
console.log("Viewport Width:", document.documentElement.clientWidth);
console.log("Viewport Height:", document.documentElement.clientHeight);
```

### Important Notes:
- `window.innerWidth` and `window.innerHeight` include the scrollbars (if visible).
- `document.documentElement.clientWidth` and `document.documentElement.clientHeight` exclude the scrollbars.
- These properties are useful for responsive design and dynamic layout adjustments.

## 16. `setTimeout`

The `setTimeout` method is used to execute a function after a specified delay (in milliseconds).

### Syntax:
```javascript
setTimeout(function, delay, arg1, arg2, ...);
```

- `function`: The function to execute after the delay.
- `delay`: The time in milliseconds to wait before executing the function.
- `arg1, arg2, ...`: Optional arguments to pass to the function.

### Example:
```javascript
console.log("Start");

setTimeout(() => {
    console.log("Executed after 2 seconds");
}, 2000);

console.log("End");
```

### Example with Arguments:
```javascript
function greet(name) {
    console.log(`Hello, ${name}!`);
}

setTimeout(greet, 3000, "John"); // Executes greet("John") after 3 seconds
```

### Clearing a Timeout:
You can cancel a timeout using `clearTimeout()`.

```javascript
let timeoutId = setTimeout(() => {
    console.log("This will not execute");
}, 5000);

clearTimeout(timeoutId); // Cancels the timeout
```

### Important Notes:
- The delay is specified in milliseconds (1 second = 1000 milliseconds).
- The function executes only once after the delay. Use `setInterval` for repeated execution.
- The actual delay may be longer than specified due to JavaScript's single-threaded nature and other tasks in the event loop.

## 17. `clearInterval`

The `clearInterval` method is used to stop a timer that was previously created with `setInterval`.

### Syntax:
```javascript
clearInterval(intervalId);
```

- `intervalId`: The identifier of the interval you want to cancel. This ID is returned by the `setInterval` method.

### Example:
```javascript
let count = 0;

// Start an interval that logs a message every second
let intervalId = setInterval(() => {
    count++;
    console.log(`Count: ${count}`);
    if (count === 5) {
        clearInterval(intervalId); // Stops the interval after 5 iterations
        console.log("Interval cleared!");
    }
}, 1000);
```

### Important Notes:
- `clearInterval` is used to stop the execution of a repeating `setInterval` timer.
- If `clearInterval` is not called, the interval will continue to execute indefinitely.
- Always store the interval ID returned by `setInterval` to use it with `clearInterval`.

### Example with `setInterval` and `clearInterval`:
```javascript
let intervalId = setInterval(() => {
    console.log("This will repeat every 2 seconds");
}, 2000);

// Stop the interval after 10 seconds
setTimeout(() => {
    clearInterval(intervalId);
    console.log("Interval stopped!");
}, 10000);
```
## 18. DOM (Document Object Model)

The DOM is a programming interface for web documents. It represents the structure of a document as a tree of objects, allowing JavaScript to interact with and manipulate HTML and CSS.

---

### 18.1 Accessing DOM Elements

You can access elements in the DOM using various methods:

#### `getElementById()`
Selects an element by its `id` attribute.
```javascript
let element = document.getElementById("myId");
console.log(element);
```

#### `getElementsByClassName()`
Selects all elements with a specific class name.
```javascript
let elements = document.getElementsByClassName("myClass");
console.log(elements); // Returns an HTMLCollection
```

#### `getElementsByTagName()`
Selects all elements with a specific tag name.
```javascript
let elements = document.getElementsByTagName("div");
console.log(elements); // Returns an HTMLCollection
```

#### `querySelector()`
Selects the first element that matches a CSS selector.
```javascript
let element = document.querySelector(".myClass");
console.log(element);
```

#### `querySelectorAll()`
Selects all elements that match a CSS selector.
```javascript
let elements = document.querySelectorAll(".myClass");
console.log(elements); // Returns a NodeList
```

---

### 18.2 Modifying DOM Elements

You can modify the content, attributes, and styles of DOM elements.

#### Changing Content
```javascript
let element = document.getElementById("myId");
element.textContent = "New Content"; // Changes text content
element.innerHTML = "<b>Bold Content</b>"; // Changes HTML content
```

#### Changing Attributes
```javascript
let element = document.getElementById("myId");
element.setAttribute("class", "newClass"); // Sets a new attribute
console.log(element.getAttribute("class")); // Gets the value of an attribute
element.removeAttribute("class"); // Removes an attribute
```

#### Changing Styles
```javascript
let element = document.getElementById("myId");
element.style.color = "red"; // Changes text color
element.style.backgroundColor = "yellow"; // Changes background color
```

---

### 18.3 Adding and Removing Elements

#### Adding Elements
```javascript
let newElement = document.createElement("div");
newElement.textContent = "I am a new element";
document.body.appendChild(newElement); // Adds the new element to the body
```

#### Removing Elements
```javascript
let element = document.getElementById("myId");
element.remove(); // Removes the element
```

---

### 18.4 Event Handling

You can add event listeners to DOM elements to handle user interactions.

#### Adding an Event Listener
```javascript
let button = document.getElementById("myButton");
button.addEventListener("click", () => {
    console.log("Button clicked!");
});
```

#### Removing an Event Listener
```javascript
function handleClick() {
    console.log("Button clicked!");
}

button.addEventListener("click", handleClick);
button.removeEventListener("click", handleClick); // Removes the event listener
```

---

### 18.5 Traversing the DOM

You can navigate through the DOM tree using various properties.

#### Parent Node
```javascript
let child = document.getElementById("child");
console.log(child.parentNode); // Gets the parent node
```

#### Child Nodes
```javascript
let parent = document.getElementById("parent");
console.log(parent.childNodes); // Gets all child nodes (including text nodes)
console.log(parent.children); // Gets only element nodes
```

#### Sibling Nodes
```javascript
let element = document.getElementById("myId");
console.log(element.nextSibling); // Gets the next sibling (including text nodes)
console.log(element.previousSibling); // Gets the previous sibling
console.log(element.nextElementSibling); // Gets the next element sibling
console.log(element.previousElementSibling); // Gets the previous element sibling
```

---

### 18.6 Common DOM Events

Here are some commonly used DOM events:

| Event Type      | Description                          |
|------------------|--------------------------------------|
| `click`         | Triggered when an element is clicked |
| `mouseover`     | Triggered when the mouse hovers over an element |
| `mouseout`      | Triggered when the mouse leaves an element |
| `keydown`       | Triggered when a key is pressed      |
| `keyup`         | Triggered when a key is released     |
| `load`          | Triggered when the page finishes loading |
| `submit`        | Triggered when a form is submitted   |
| `change`        | Triggered when the value of an input changes |
| `focus`         | Triggered when an element gains focus |
| `blur`          | Triggered when an element loses focus |

#### Example:
```javascript
let input = document.getElementById("myInput");
input.addEventListener("change", (event) => {
    console.log("Input value changed to:", event.target.value);
});
```

---

### 18.7 DOM Properties vs Attributes

- **Attributes** are defined in the HTML and can be accessed using `getAttribute` and `setAttribute`.
- **Properties** are part of the DOM object and can be accessed directly.

#### Example:
```javascript
let input = document.getElementById("myInput");
console.log(input.getAttribute("value")); // Gets the initial value from HTML
console.log(input.value); // Gets the current value from the DOM
```

---

### 18.8 Performance Tips for DOM Manipulation

- Minimize DOM access by storing references to elements.
- Use `documentFragment` to batch DOM updates.
- Avoid inline styles; use CSS classes instead.
- Use `requestAnimationFrame` for animations.

#### Example with `documentFragment`:
```javascript
let fragment = document.createDocumentFragment();
for (let i = 0; i < 10; i++) {
    let newElement = document.createElement("div");
    newElement.textContent = `Item ${i}`;
    fragment.appendChild(newElement);
}
document.body.appendChild(fragment); // Adds all elements at once
```
### 18.9 More About DOM Events

DOM events are actions or occurrences that happen in the browser, such as a user clicking a button, hovering over an element, or pressing a key. JavaScript can listen for these events and execute code in response.

---

#### 18.9.1 Event Types

Here are some common event types and their descriptions:

| Event Type      | Description                          |
|------------------|--------------------------------------|
| `click`         | Triggered when an element is clicked |
| `dblclick`      | Triggered when an element is double-clicked |
| `mouseover`     | Triggered when the mouse hovers over an element |
| `mouseout`      | Triggered when the mouse leaves an element |
| `mousedown`     | Triggered when a mouse button is pressed |
| `mouseup`       | Triggered when a mouse button is released |
| `keydown`       | Triggered when a key is pressed      |
| `keyup`         | Triggered when a key is released     |
| `keypress`      | Triggered when a key is pressed (deprecated, use `keydown` or `keyup`) |
| `focus`         | Triggered when an element gains focus |
| `blur`          | Triggered when an element loses focus |
| `submit`        | Triggered when a form is submitted   |
| `change`        | Triggered when the value of an input changes |
| `load`          | Triggered when the page or an image finishes loading |
| `resize`        | Triggered when the browser window is resized |
| `scroll`        | Triggered when the user scrolls the page |

---

#### 18.9.2 Event Listener Example

You can use `addEventListener` to attach an event listener to an element.

```javascript
let button = document.getElementById("myButton");

// Add a click event listener
button.addEventListener("click", () => {
    console.log("Button clicked!");
});
```

---

#### 18.9.3 Event Object

When an event occurs, an event object is automatically passed to the event handler. This object contains information about the event.

```javascript
let button = document.getElementById("myButton");

button.addEventListener("click", (event) => {
    console.log("Event type:", event.type); // Output: click
    console.log("Target element:", event.target); // The element that triggered the event
});
```

---

#### 18.9.4 Preventing Default Behavior

You can use the `preventDefault()` method to stop the default behavior of an event.

```javascript
let link = document.getElementById("myLink");

link.addEventListener("click", (event) => {
    event.preventDefault(); // Prevents the link from navigating
    console.log("Default behavior prevented!");
});
```

---

#### 18.9.5 Event Propagation

Events in the DOM propagate in two phases:
1. **Capturing Phase**: The event starts from the root and goes down to the target element.
2. **Bubbling Phase**: The event bubbles up from the target element to the root.

You can specify the phase in which the event listener should be triggered by passing a third argument to `addEventListener`.

```javascript
let parent = document.getElementById("parent");
let child = document.getElementById("child");

// Event listener on parent
parent.addEventListener("click", () => {
    console.log("Parent clicked!");
}, true); // Capturing phase

// Event listener on child
child.addEventListener("click", () => {
    console.log("Child clicked!");
}, false); // Bubbling phase
```

---

#### 18.9.6 Stopping Event Propagation

You can use the `stopPropagation()` method to stop the event from propagating further.

```javascript
let parent = document.getElementById("parent");
let child = document.getElementById("child");

parent.addEventListener("click", () => {
    console.log("Parent clicked!");
});

child.addEventListener("click", (event) => {
    event.stopPropagation(); // Stops the event from reaching the parent
    console.log("Child clicked!");
});
```

---

#### 18.9.7 Delegating Events

Event delegation is a technique where you attach a single event listener to a parent element to handle events for its child elements. This is useful for dynamically added elements.

```javascript
let parent = document.getElementById("parent");

// Event delegation
parent.addEventListener("click", (event) => {
    if (event.target && event.target.tagName === "BUTTON") {
        console.log("Button clicked:", event.target.textContent);
    }
});

// Adding buttons dynamically
let button1 = document.createElement("button");
button1.textContent = "Button 1";
parent.appendChild(button1);

let button2 = document.createElement("button");
button2.textContent = "Button 2";
parent.appendChild(button2);
```

---

#### 18.9.8 Keyboard Events

You can listen for keyboard events like `keydown`, `keyup`, and `keypress`.

```javascript
document.addEventListener("keydown", (event) => {
    console.log("Key pressed:", event.key); // Logs the key pressed
    console.log("Key code:", event.code); // Logs the physical key code
});
```

---

#### 18.9.9 Mouse Events

Mouse events include `click`, `dblclick`, `mouseover`, `mouseout`, `mousedown`, and `mouseup`.

```javascript
let box = document.getElementById("box");

box.addEventListener("mouseover", () => {
    console.log("Mouse entered the box!");
});

box.addEventListener("mouseout", () => {
    console.log("Mouse left the box!");
});
```

---

#### 18.9.10 Form Events

Form events include `submit`, `change`, `focus`, and `blur`.

```javascript
let form = document.getElementById("myForm");

// Submit event
form.addEventListener("submit", (event) => {
    event.preventDefault(); // Prevents form submission
    console.log("Form submitted!");
});

// Change event
let input = document.getElementById("myInput");
input.addEventListener("change", () => {
    console.log("Input value changed:", input.value);
});
```

---

### Summary of Event Handling

- Use `addEventListener` to attach event listeners.
- Use `event.preventDefault()` to stop default behavior.
- Use `event.stopPropagation()` to stop event propagation.
- Use event delegation for dynamically added elements.
- Always clean up event listeners when they are no longer needed to avoid memory leaks.

## Example: Button Click to Show Alert and Redirect to Another Page

This example demonstrates how to show an alert message when a button is clicked and then redirect the user to another page.

### HTML Code
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Button Click Example</title>
</head>
<body>
    <button onclick="call()">Click Me!</button>
</body>
<script src="index.js"></script>
</html>
```

### JavaScript Code
```javascript
function call() {
    alert("You are being redirected...");
    window.location.href = "output.html";
}
```

### Explanation
1. **HTML Button**: The `<button>` element has an `onclick` attribute that calls the `call()` function when clicked.
2. **JavaScript Function**: The `call()` function:
   - Displays an alert message using `alert()`.
   - Redirects the user to `output.html` using `window.location.href`.

### Output
- When the button is clicked, an alert box with the message "You are being redirected..." is displayed.
- After dismissing the alert, the browser navigates to `output.html`.
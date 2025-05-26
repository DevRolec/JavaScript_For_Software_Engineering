# JavaScript for Software Engineering
# 📘 Module 1: Core JavaScript & Language Essentials

## Week 1: Variables, Scope, and Hoisting

### Lesson 1.1: Variables (var, let, const)
**Topics:**
- Variable declaration rules
- Differences: `var`, `let`, `const`

**Practice:**
```js
var a = 1;
let b = 2;
const c = 3;
a = 10; b = 20;
// c = 30;
console.log(a, b, c);
```
---
Lesson 1.2: Scope (Global, Local, Block)
Practice:

js
Copy
Edit
function testScope() {
  let x = 1;
  if (true) {
    let x = 2;
    console.log("Inside:", x);
  }
  console.log("Outside:", x);
}

Lesson 1.3: Hoisting
Practice:

js
Copy
Edit
console.log(hoistedVar);
var hoistedVar = "I'm hoisted";

console.log(hoistedLet);
let hoistedLet = "I'm not hoisted";
---
Week 2: Data Types & Type Conversions
Lesson 2.1: Primitives vs References
Practice:

js
Copy
Edit
const a = [1, 2];
const b = a;
b.push(3);
console.log(a);
Lesson 2.2: Type Coercion vs Conversion
Practice:

js
Copy
Edit
console.log(5 + "5");
console.log(Number("123"));
console.log(Boolean(0));
---
Week 3: Control Flow
Lesson 3.1: Conditionals
Practice:

js
Copy
Edit
let age = 20;
let message = age >= 18 ? "Adult" : "Minor";
console.log(message);
Lesson 3.2: Loops
Practice:

js
Copy
Edit
for (let i = 1; i <= 10; i++) {
  if (i % 2 === 0) continue;
  console.log(i);
}
---
Week 4: Functions and Closures
Lesson 4.1: Function Types
Practice:

js
Copy
Edit
const add = (a, b) => a + b;
console.log(add(3, 4));
Lesson 4.2: Closures & IIFE
Practice:

js
Copy
Edit
function outer() {
  let count = 0;
  return function inner() {
    count++;
    console.log(count);
  };
}
const counter = outer();
counter();
counter();

(function() {
  console.log("IIFE ran!");
})();
---
Week 5: ES6+ Features
Lesson 5.1: let/const and Block Scope
js
Copy
Edit
{
  let scoped = "Inside block";
  console.log(scoped);
}
Lesson 5.2: Template Literals
js
Copy
Edit
let name = "Sara";
let greeting = `Hello, ${name}!`;
console.log(greeting);
Lesson 5.3: Destructuring
js
Copy
Edit
const user = { name: "Tom", age: 25 };
const { name, age } = user;

const nums = [1, 2, 3];
const [first, second] = nums;
✅ Final Project: lodash-lite
Build utility functions:

_.isEmpty(obj)

_.cloneDeep(obj)

_.debounce(func, delay)

_.uniq(arr)

_.flatten(arr)

php-template
Copy
Edit

---

## 🌐 HTML VERSION

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Module 1: JavaScript Core Essentials</title>
  <style>
    body { font-family: sans-serif; margin: 40px; line-height: 1.6; }
    code, pre { background-color: #f3f3f3; padding: 8px; border-radius: 4px; display: block; }
    h1, h2, h3 { color: #333; }
  </style>
</head>
<body>

  <h1>📘 Module 1: Core JavaScript & Language Essentials</h1>

  <h2>Week 1: Variables, Scope, and Hoisting</h2>
  <h3>Lesson 1.1: Variables</h3>
  <pre><code>
var a = 1;
let b = 2;
const c = 3;
a = 10; b = 20;
// c = 30;
console.log(a, b, c);
  </code></pre>

  <h3>Lesson 1.2: Scope</h3>
  <pre><code>
function testScope() {
  let x = 1;
  if (true) {
    let x = 2;
    console.log("Inside:", x);
  }
  console.log("Outside:", x);
}
  </code></pre>

  <h3>Lesson 1.3: Hoisting</h3>
  <pre><code>
console.log(hoistedVar);
var hoistedVar = "I'm hoisted";

console.log(hoistedLet);
let hoistedLet = "I'm not hoisted";
  </code></pre>

  <h2>Week 2: Data Types & Type Conversions</h2>
  <pre><code>
const a = [1, 2];
const b = a;
b.push(3);
console.log(a);
  </code></pre>

  <pre><code>
console.log(5 + "5");
console.log(Number("123"));
console.log(Boolean(0));
  </code></pre>

  <h2>✅ Final Project: lodash-lite</h2>
  <p>Build utility functions:</p>
  <ul>
    <li>_.isEmpty(obj)</li>
    <li>_.cloneDeep(obj)</li>
    <li>_.debounce(func, delay)</li>
    <li>_.uniq(arr)</li>
    <li>_.flatten(arr)</li>
  </ul>

</body>
</html>
```
---
# 🔁 MODULE 2: Asynchronous Programming

Welcome to Module 2! In this section, you'll dive into the world of asynchronous JavaScript, where you'll learn how to build responsive web apps that don't freeze when fetching data or waiting for long-running processes. You’ll finish this module by creating a full Weather Dashboard using the OpenWeatherMap API.

📚 Topics Covered
Callback Functions

Promises

Async/Await Pattern

Fetch API

Error Handling

Throttling and Debouncing

Event Loop & Microtasks

Final Project: Weather Dashboard

🌀 1. Callback Functions
🔎 What is a Callback?
A callback is a function passed as an argument to another function, to be executed later.

js
Copy
Edit
function fetchData(callback) {
  setTimeout(() => {
    callback('Data loaded!');
  }, 1000);
}

fetchData((message) => {
  console.log(message); // "Data loaded!"
});
✅ Practice
Write a loadProfile(callback) function that waits 2 seconds and then logs "Profile Loaded".

Chain multiple callbacks to simulate a step-by-step loading process (e.g., authenticate → fetch profile → show dashboard).

🔐 2. Promises
🔎 What is a Promise?
A Promise represents a value that may be available now, later, or never.

js
Copy
Edit
const promise = new Promise((resolve, reject) => {
  setTimeout(() => resolve("Data is here!"), 1000);
});

promise.then(data => console.log(data));
✅ Practice
Create a function getPosts() that returns a Promise resolved after 2 seconds.

Chain .then() to log the post list.

⏳ 3. Async/Await Pattern
🔎 What is Async/Await?
It’s syntactic sugar over Promises that makes your async code look synchronous and easier to read.

js
Copy
Edit
async function loadData() {
  try {
    const result = await fetchData();
    console.log(result);
  } catch (err) {
    console.error(err);
  }
}
✅ Practice
Convert your getPosts() from earlier to use async/await.

Create a sequence of await calls that depend on each other.

🌐 4. Fetch API
🔎 What is Fetch?
The fetch() method lets you make HTTP requests in the browser.

js
Copy
Edit
fetch('https://api.example.com/data')
  .then(res => res.json())
  .then(data => console.log(data));
✅ Practice
Use fetch() to call https://jsonplaceholder.typicode.com/posts.

Display the first 3 post titles in the browser.

⚠️ 5. Error Handling
🔎 Why is it Important?
Handle errors gracefully so your app doesn’t break when a server fails.

js
Copy
Edit
fetch('https://wrong-url.com')
  .then(response => {
    if (!response.ok) throw new Error("Fetch failed!");
    return response.json();
  })
  .catch(error => console.error(error));
✅ Practice
Break a fetch() on purpose and catch the error.

Use try/catch inside async functions.

⚙️ 6. Throttling and Debouncing
🔎 What’s the Difference?
Throttling: Limits function calls to once every X ms.

Debouncing: Waits X ms after the last function call.

js
Copy
Edit
function debounce(fn, delay) {
  let timer;
  return function (...args) {
    clearTimeout(timer);
    timer = setTimeout(() => fn.apply(this, args), delay);
  };
}
✅ Practice
Add a debounced search input using setTimeout.

Add a throttled window resize logger using setInterval.

🧠 7. Event Loop & Microtasks
🔎 How JS Handles Async Code?
JS has an event loop that manages sync code, microtasks (Promises), and macrotasks (setTimeout, etc.).

js
Copy
Edit
console.log('Start');
setTimeout(() => console.log('Timeout'), 0);
Promise.resolve().then(() => console.log('Promise'));
console.log('End');
// Output: Start, End, Promise, Timeout
✅ Practice
Write your own example mixing Promise, setTimeout, and console.log.

Predict the output before running.

🎯 Project: Weather Dashboard using OpenWeatherMap API
💡 Project Brief
Build a dashboard that:

Takes city input

Fetches weather data using OpenWeatherMap

Displays current weather, temperature, and icon

🔨 Features
Debounced search input

Error handling for invalid cities

Async/Await & Fetch to retrieve weather

Dynamic DOM update

🔗 API Link
OpenWeatherMap API

🏁 Stretch Goals
Add 5-day forecast

Show weather history using localStorage

Add dark/light mode toggle
---

# 🧱Module 3: DOM Manipulation & Browser APIs
---
This module focuses on how JavaScript interacts with the structure and content of web pages (the DOM) and how to leverage built-in browser functionalities to create dynamic and interactive web applications.

## 1. DOM Selection & Traversal
The Document Object Model (DOM) is a programming interface for web documents. It represents the page as a structured tree of objects. DOM selection allows us to target specific HTML elements, and traversal lets us navigate between these elements.

DOM Selection Methods:

document.getElementById('id'): Selects a single element by its unique id attribute.

JavaScript

const myElement = document.getElementById('myId');
console.log(myElement);
document.getElementsByClassName('class'): Returns an HTMLCollection (live updating) of all elements with the given class name.

JavaScript

const allButtons = document.getElementsByClassName('button');
console.log(allButtons);
document.getElementsByTagName('tag'): Returns an HTMLCollection (live updating) of all elements with the given tag name.

JavaScript

const allParagraphs = document.getElementsByTagName('p');
console.log(allParagraphs);
document.querySelector('selector'): Returns the first element that matches the specified CSS selector.

JavaScript

const firstLink = document.querySelector('a');
const specialDiv = document.querySelector('#special .item');
console.log(firstLink, specialDiv);
document.querySelectorAll('selector'): Returns a NodeList (static) of all elements that match the specified CSS selector.

JavaScript

const allLinks = document.querySelectorAll('a');
console.log(allLinks);
DOM Traversal Properties:

Once you have an element, you can navigate the DOM tree using its properties:

parentNode: The parent node of the element.
childNodes: A NodeList of the element's direct children.
children: An HTMLCollection of the element's direct element children.
firstChild: The first child node.
firstElementChild: The first element child.
lastChild: The last child node.
lastElementChild: The last element child.
nextSibling: The next node at the same level.
nextElementSibling: The next element at the same level.
previousSibling: The previous node at the same level.
previousElementSibling: The previous element at the same level.
HTML

<div id="container">
  <p>First paragraph</p>
  <span class="highlight">Important text</span>
  <p>Second paragraph</p>
</div>

<script>
  const container = document.getElementById('container');
  console.log(container.children); // HTMLCollection [p, span.highlight, p]
  console.log(container.firstElementChild); // <p>First paragraph</p>

  const highlightSpan = document.querySelector('.highlight');
  console.log(highlightSpan.parentNode); // <div id="container">...</div>
  console.log(highlightSpan.nextElementSibling); // <p>Second paragraph</p>
</script>
Practice Assignment 1:

Create an HTML file with a <ul> containing at least three <li> items. Give the <ul> an id. Give one of the <li> items a class.
Write JavaScript code to:
Select the <ul> element using its id.
Select all <li> elements.
Select the <li> element with the specific class.
Log the parentNode of the first <li> element.
Log the nextElementSibling of the <li> with the class.
2. Event Handling (Delegation, Bubbling/Capturing)
Event handling allows us to make our web pages interactive by responding to user actions (like clicks, mouse movements, key presses) or browser events.

Adding Event Listeners:

The primary way to handle events is using the addEventListener() method:

JavaScript

element.addEventListener('eventType', callbackFunction, useCapture);
eventType: A string representing the type of event (e.g., 'click', 'mouseover', 'keydown').
callbackFunction: The function to execute when the event occurs.
useCapture (optional): A boolean indicating whether to use capturing or bubbling (default is false - bubbling).
HTML

<button id="myButton">Click Me</button>
<script>
  const button = document.getElementById('myButton');
  button.addEventListener('click', function() {
    console.log('Button clicked!');
  });
</script>
Event Bubbling and Capturing:

When an event occurs on an HTML element, it goes through two phases:

Capturing Phase: The event travels down the DOM tree from the window to the target element. Event listeners attached in the capturing phase are triggered first.
Target Phase: The event reaches the target element where it originated. Event listeners attached directly to the target are triggered.
Bubbling Phase: The event travels back up the DOM tree from the target element to the window. Event listeners attached in the bubbling phase are triggered.
The default behavior is bubbling.

HTML

<div id="outer">
  <div id="inner">Click Here</div>
</div>

<script>
  const outerDiv = document.getElementById('outer');
  const innerDiv = document.getElementById('inner');

  outerDiv.addEventListener('click', function() {
    console.log('Outer div clicked (bubbling)');
  });

  innerDiv.addEventListener('click', function() {
    console.log('Inner div clicked (bubbling)');
  });

  outerDiv.addEventListener('click', function() {
    console.log('Outer div clicked (capturing)');
  }, true); // true for capturing

  innerDiv.addEventListener('click', function() {
    console.log('Inner div clicked (capturing)');
  }, true); // true for capturing
</script>
When you click the "Click Here" text, you'll see the logs in this order:

Outer div clicked (capturing)
Inner div clicked (capturing)
Inner div clicked (bubbling)
Outer div clicked (bubbling)
Event Delegation:

Event delegation is a technique where you attach a single event listener to a parent element to handle events for all its current and future descendant elements. This is efficient, especially for dynamically added elements.

HTML

<ul id="item-list">
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>

<button id="addItem">Add Item</button>

<script>
  const itemList = document.getElementById('item-list');
  const addItemButton = document.getElementById('addItem');
  let itemCount = 4;

  itemList.addEventListener('click', function(event) {
    if (event.target.tagName === 'LI') {
      console.log(`You clicked on: ${event.target.textContent}`);
    }
  });

  addItemButton.addEventListener('click', function() {
    const newItem = document.createElement('li');
    newItem.textContent = `Item ${itemCount++}`;
    itemList.appendChild(newItem);
  });
</script>
In this example, we only attach one click listener to the <ul>. When any <li> inside it is clicked, the event bubbles up to the <ul>, and we check if the event.target (the originating element of the event) is an <li>.

Practice Assignment 2:

Create an HTML file with a button. When the button is clicked, change the text content of a paragraph on the page.
Create an HTML file with a <ul> and several <li> items. Use event delegation to log the text content of whichever <li> is clicked. Add a button that dynamically adds new <li> elements to the list and ensure the click listener still works for the new items.
3. Forms and Validation
HTML forms are used to collect user input. JavaScript plays a crucial role in handling form submissions and performing client-side validation.

Accessing Form Elements:

You can select form elements using the DOM selection methods we learned earlier.

HTML

<form id="myForm">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name"><br><br>
  <label for="email">Email:</label>
  <input type="email" id="email" name="email"><br><br>
  <button type="submit">Submit</button>
</form>

<script>
  const form = document.getElementById('myForm');
  const nameInput = document.getElementById('name');
  const emailInput = document.getElementById('email');

  form.addEventListener('submit', function(event) {
    event.preventDefault(); // Prevent the default form submission

    console.log('Name:', nameInput.value);
    console.log('Email:', emailInput.value);

    // Perform validation here
  });
</script>
Form Validation:

Client-side validation improves user experience by providing immediate feedback before submitting the form to the server.

JavaScript

form.addEventListener('submit', function(event) {
  let isValid = true;

  if (nameInput.value.trim() === '') {
    alert('Name is required.');
    isValid = false;
  }

  if (emailInput.value.trim() === '' || !isValidEmail(emailInput.value)) {
    alert('Please enter a valid email address.');
    isValid = false;
  }

  if (!isValid) {
    event.preventDefault(); // Prevent submission if validation fails
  } else {
    alert('Form submitted successfully!');
    // You would typically send the data to the server here
  }
});

function isValidEmail(email) {
  // Basic email validation regex
  const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  return emailRegex.test(email);
}
HTML5 Form Validation Attributes:

HTML5 provides built-in validation attributes like required, minlength, maxlength, type="email", pattern, etc. The browser automatically handles some of this validation. You can access the validity state of form elements using the validity property.

HTML

<form id="myFormHTML5">
  <label for="name">Name:</label>
  <input type="text" id="nameHTML5" name="name" required minlength="3"><br><br>
  <label for="email">Email:</label>
  <input type="email" id="emailHTML5" name="email" required><br><br>
  <button type="submit">Submit</button>
</form>

<script>
  const formHTML5 = document.getElementById('myFormHTML5');
  const nameInputHTML5 = document.getElementById('nameHTML5');
  const emailInputHTML5 = document.getElementById('emailHTML5');

  formHTML5.addEventListener('submit', function(event) {
    if (!formHTML5.checkValidity()) {
      event.preventDefault();
      alert('Please fill out the form correctly.');
    } else {
      alert('Form submitted (HTML5 validation passed)!');
    }
  });

  nameInputHTML5.addEventListener('invalid', function(event) {
    if (nameInputHTML5.validity.valueMissing) {
      event.target.setCustomValidity('Please enter your name.');
    } else if (nameInputHTML5.validity.minLength) {
      event.target.setCustomValidity(`Name must be at least ${nameInputHTML5.minLength} characters long.`);
    } else {
      event.target.setCustomValidity(''); // Reset custom validity
    }
  });

  emailInputHTML5.addEventListener('invalid', function(event) {
    if (emailInputHTML5.validity.valueMissing) {
      event.target.setCustomValidity('Please enter your email.');
    } else if (emailInputHTML5.validity.typeMismatch) {
      event.target.setCustomValidity('Please enter a valid email address.');
    } else {
      event.target.setCustomValidity('');
    }
  });
</script>
Practice Assignment 3:

Create an HTML form with fields for name (required, min length 3), email (required, valid format), and a password (required, min length 6).
Use JavaScript to perform client-side validation on form submission. Display appropriate error messages if any field is invalid.
4. localStorage and sessionStorage
These Web Storage APIs provide mechanisms for web applications to store data locally within the user's browser.

localStorage: Stores data with no expiration date. It's available even after the browser window is closed and reopened.
sessionStorage: Stores data for the duration of the current session. The data is cleared when the browser tab or window is closed.
Basic Operations:

setItem(key, value): Adds or updates a key/value pair. Values are stored as strings.
getItem(key): Retrieves the value associated with the given key. Returns null if the key does not exist.
removeItem(key): Removes the key/value pair associated with the given key.
clear(): Removes all key/value pairs stored in the storage.
JavaScript

// localStorage example
localStorage.setItem('username', 'john.doe');
const storedUsername = localStorage.getItem('username');
console.log('Username from localStorage:', storedUsername);
localStorage.removeItem('username');
// localStorage.clear();

// sessionStorage example
sessionStorage.setItem('sessionId', '12345');
const sessionId = sessionStorage.getItem('sessionId');
console.log('Session ID from sessionStorage:', sessionId);
// sessionStorage.removeItem('sessionId');
// sessionStorage.clear();
You can store more complex data by serializing it to JSON:

JavaScript

const user = { name: 'Alice', age: 30 };
localStorage.setItem('userData', JSON.stringify(user));

const storedUserString = localStorage.getItem('userData');
const storedUser = JSON.parse(storedUserString);
console.log('Stored user:', storedUser);
Practice Assignment 4:

Create a simple web page with a text input and a button. When the button is clicked, save the text from the input into localStorage.
On page load, check if there's any data in localStorage from the previous step. If so, display it on the page.
5. History API, Location API
These APIs allow you to interact with the browser's history and the current URL.

Location API (window.location):

Provides information about the current URL and allows you to navigate to new URLs.

location.href: The entire URL.
location.protocol: The protocol of the URL (e.g., "http:", "https:").
location.host: The hostname and port of the URL.
location.pathname: The path part of the URL.
location.search: The query string part of the URL (starting with "?").
location.hash: The fragment identifier part of the URL (starting with "#").
location.assign(url): Loads a new document at the given URL. Records the navigation in the browser's history.
location.replace(url): Loads a new document at the given URL. Does not record the navigation in the browser's history (you can't go back).
location.reload(): Reloads the current page.
JavaScript

console.log('Current URL:', window.location.href);
console.log('Pathname:', window.location.pathname);

// To navigate to a new page:
// window.location.assign('https://www.example.com');
// window.location.replace('https://www.example.com');
// window.location.reload();
History API (window.history):

Allows you to manipulate the browser's session history (the stack of pages the user has visited).

history.back(): Goes back one page in the history.
history.forward(): Goes forward one page in the history.
history.go(n): Goes to the nth page in the history (e.g., -1 is back, 1 is forward).
history.pushState(state, title, url): Adds a new state to the history stack. The browser URL changes to the url, but the page is not reloaded. You can associate state data with this history entry.
history.replaceState(state, title, url): Modifies the current history entry. Similar to pushState but doesn't create a new entry.
The popstate event is fired when the active history entry changes (e.g., when the user clicks the back or forward button, or when history.go(), history.back(), or history.forward() are called).

JavaScript

// Example using pushState
function navigate(page) {
  const newUrl = `/${page}`;
  history.pushState({ page }, page, newUrl);
  updateContent(page); // Your function to load content based on the page
}

window.addEventListener('popstate', function(event) {
  console.log('Popstate event:', event);
  if (event.state && event.state.page) {
    updateContent(event.


---
# 🧱 MODULE 4: Modular Code, Tooling & Architecture

Okay, let's delve into Module 4: Modular Code, Tooling & Architecture. This module focuses on structuring your JavaScript code effectively and using modern development tools to streamline your workflow.

Module 4: Modular Code, Tooling & Architecture
1. ES Modules and CommonJS
Modularity is crucial for organizing JavaScript code into reusable and maintainable pieces. JavaScript has evolved in how it handles modules.

CommonJS:

Historically, Node.js adopted the CommonJS module system. You've likely seen this if you've worked with Node.js.

require(): To import modules.
module.exports: To export modules.
JavaScript

// math.js (CommonJS)
function add(a, b) {
  return a + b;
}

function subtract(a, b) {
  return a - b;
}

module.exports = {
  add: add,
  subtract: subtract
};

// main.js (CommonJS)
const math = require('./math.js');
console.log(math.add(5, 3)); // Output: 8
console.log(math.subtract(10, 4)); // Output: 6
ES Modules (ESM):

Modern JavaScript (ES6 and later) introduced its native module system. This is the standard for browser-based JavaScript and is increasingly supported in Node.js.

import: To import modules.
export: To export modules (named or default).
JavaScript

// math.js (ESM)
export function add(a, b) {
  return a + b;
}

export function subtract(a, b) {
  return a - b;
}

// main.js (ESM)
import { add, subtract } from './math.js';
console.log(add(5, 3)); // Output: 8
console.log(subtract(10, 4)); // Output: 6

// Or import everything as an object:
// import * as math from './math.js';
// console.log(math.add(5, 3));
You can also have a default export:

JavaScript

// greeting.js (ESM)
const message = "Hello!";
export default message;

// main.js (ESM)
import greeting from './greeting.js';
console.log(greeting); // Output: Hello!
Browsers require special handling for ES Modules, typically using the <script type="module"> tag in your HTML.

HTML

<!DOCTYPE html>
<html>
<head>
  <title>ES Modules in Browser</title>
</head>
<body>
  <script type="module" src="main.js"></script>
</body>
</html>
Practice Assignment 1:

Create two JavaScript files (utils.js and app.js).
In utils.js, define a function that capitalizes a string and another that reverses a string. Export these functions using ES Modules.
In app.js, import these functions and use them to manipulate a string, then log the results to the console. Create an HTML file to run app.js as an ES Module in the browser.
2. NPM, Yarn, Package Management
When building larger projects, you'll often rely on third-party libraries. Package managers help you manage these dependencies. npm (Node Package Manager) and Yarn are the most popular ones for JavaScript.

npm: Comes bundled with Node.js.

Yarn: Another package manager developed by Facebook, Google, Exponent, and Tilde. It aims for speed and reliability.

Key Concepts:

package.json: A file at the root of your project that tracks the project's dependencies, scripts, name, version, etc.
node_modules: A directory where the installed packages and their dependencies reside.
Common Commands:

npm:

npm init -y: Initializes a new npm project with default settings, creating a package.json file.
npm install <package-name> or npm i <package-name>: Installs a specific package and adds it to package.json.
npm install: Installs all dependencies listed in package.json.
npm uninstall <package-name>: Uninstalls a package and removes it from package.json.
npm install --save-dev <package-name> or npm i -D <package-name>: Installs a package as a development dependency (used for tooling like linters, testers).
npm run <script-name>: Executes a script defined in the "scripts" section of package.json.
Yarn:

yarn init -y: Initializes a new Yarn project with default settings.
yarn add <package-name>: Installs a package and adds it to package.json and the yarn.lock file.
yarn: Installs all dependencies listed in package.json.
yarn remove <package-name>: Uninstalls a package.
yarn add --dev <package-name> or yarn add -D <package-name>: Installs a development dependency.
yarn <script-name>: Executes a script defined in the "scripts" section of package.json.
Example:

Initialize a new npm project: npm init -y
Install the lodash utility library: npm install lodash (or yarn add lodash)
In your JavaScript file:
JavaScript

// Using lodash (assuming you're in a Node.js environment or using a bundler)
import _ from 'lodash';

const numbers = [1, 2, 2, 3, 4, 4, 5];
const uniqueNumbers = _.uniq(numbers);
console.log(uniqueNumbers); // Output: [1, 2, 3, 4, 5]
Practice Assignment 2:

Create a new project directory.
Initialize an npm (or Yarn) project.
Install the moment library (for date manipulation).
Write a JavaScript file that imports moment and uses it to display the current date and time in a specific format. Run this file (you might need Node.js for this step if not using a bundler yet).
3. Webpack, Vite, Rollup
These are module bundlers. In modern web development, you often write modular JavaScript, CSS, and other assets. Browsers, however, don't natively understand all module formats or benefit from having many small files. Bundlers solve this by:

Bundling: Taking your modules and their dependencies and generating static assets (often single or a few .js files, .css files, etc.) that are optimized for the browser.
Transforming: They can also transform your code using loaders and plugins (e.g., transpiling modern JavaScript, processing CSS).
Webpack: A powerful and highly configurable module bundler.

Vite: A newer bundler that leverages native browser ES Modules during development for incredibly fast hot module replacement (HMR) and uses Rollup for production builds.

Rollup: Primarily focused on bundling JavaScript libraries. It's known for producing smaller bundles.

Let's look at a basic Webpack setup:

Install Webpack and its CLI as dev dependencies:

Bash

npm install --save-dev webpack webpack-cli
# or
yarn add --dev webpack webpack-cli
Create a webpack.config.js file in your project root:

JavaScript

// webpack.config.js
const path = require('path');

module.exports = {
  mode: 'development', // or 'production'
  entry: './src/index.js', // Your main entry point
  output: {
    filename: 'bundle.js', // The output bundle file name
    path: path.resolve(__dirname, 'dist'), // Output directory
  },
};
Create a src folder with an index.js file (and any other modules).

Add a script to your package.json:

JSON

"scripts": {
  "build": "webpack --config webpack.config.js"
}
Run the build command: npm run build (or yarn build). This will create a dist folder with bundle.js.

In your HTML, link to the bundled file:

HTML

<!DOCTYPE html>
<html>
<head>
  <title>Webpack Example</title>
</head>
<body>
  <script src="./dist/bundle.js"></script>
</body>
</html>
Vite offers a more streamlined developer experience out of the box. To try Vite:

Create a new Vite project:

Bash

npm create vite@latest my-vite-app -- --template vanilla
cd my-vite-app
npm install
npm run dev
Vite will typically handle bundling and serving your application with hot module replacement without extensive configuration.

Practice Assignment 3:

Set up a simple project with a few JavaScript modules that import each other.
Configure either Webpack or Vite to bundle these modules into a single file for the browser.
Create an HTML file that includes this bundled JavaScript file.
4. Transpiling with Babel
Modern JavaScript features (ES6+) are not always fully supported by all browsers. Transpilers like Babel convert newer JavaScript syntax into older, more widely compatible versions (typically ES5).

Install Babel core and the preset for the target environment (e.g., ES2015):

Bash

npm install --save-dev @babel/core @babel/preset-env
# or
yarn add --dev @babel/core @babel/preset-env
Create a .babelrc or babel.config.js file to configure Babel:

JSON

// .babelrc
{
  "presets": ["@babel/preset-env"]
}
You'll usually integrate Babel with your module bundler (Webpack, Vite, Rollup) using appropriate loaders or plugins. For Webpack, you'd use babel-loader.
Bash

npm install --save-dev babel-loader
# or
yarn add --dev babel-loader
Update your webpack.config.js to use babel-loader:
JavaScript

// webpack.config.js
const path = require('path');

module.exports = {
  mode: 'development',
  entry: './src/index.js',
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist'),
  },
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        use: 'babel-loader',
      },
    ],
  },
};
Now, when Webpack bundles your code, it will first pass .js files (excluding those in node_modules) through Babel for transpilation.

Practice Assignment 4:

Take the project from the previous assignment (with module bundling).
Install and configure Babel to transpile your JavaScript code.
Ensure your bundled output is now in a more widely compatible JavaScript version. You might need to use modern ES6+ syntax in your source files to see the effect of transpilation.
5. Linting with ESLint, Formatting with Prettier
Maintaining a consistent code style and catching potential errors early are crucial for team collaboration and code quality.

ESLint: A static code analysis tool used for identifying problematic patterns in JavaScript code. It helps enforce coding standards and prevent bugs.
Prettier: An opinionated code formatter that automatically formats your code to ensure consistency.
Setting up ESLint:

Install ESLint and a recommended configuration (e.g., Airbnb's style guide):

Bash

npm install --save-dev eslint eslint-config-airbnb-base eslint-plugin-import
# or
yarn add --dev eslint eslint-config-airbnb-base eslint-plugin-import
Initialize ESLint configuration:

Bash

npx eslint --init
# Follow the prompts (e.g., "To check syntax, find problems, and enforce code style", "JavaScript modules (import/export)", etc.)
# Or, if you want to use Airbnb, create a `.eslintrc.js` file:
JavaScript

// .eslintrc.js (using Airbnb style guide)
module.exports = {
  env: {
    browser: true,
    es2021: true,
    node: true,
  },
  extends: [
    'airbnb-base',
    'plugin:import/recommended',
  ],
  parserOptions: {
    ecmaVersion: 'latest',
    sourceType: 'module',
  },
  rules: {
    // Add or override rules here if needed
  },
};
Add an npm script to run ESLint:
JSON

// package.json
"scripts": {
  "lint": "eslint ."
}
Run the linter: npm run lint. It will report any style or potential error issues.
Setting up Prettier:

Install Prettier:

Bash

npm install --save-dev prettier
# or
yarn add --dev prettier
Create a .prettierrc.js (or .prettierrc, etc.) to configure Prettier (optional, as it has default settings):

JavaScript

// .prettierrc.js
module.exports = {
  semi: false,
  singleQuote: true,
  trailingComma: 'es5',
};
Add an npm script to run Prettier:
JSON

// package.json
"scripts": {
  "format": "prettier --write ."
}
Run the formatter: npm run format. This will automatically format your code.
You often integrate ESLint and Prettier so they work well together. You might need additional configurations like eslint-config-prettier and eslint-plugin-prettier.

Practice Assignment 5:

Set up ESLint and Prettier in your project.
Write some JavaScript code with intentional style inconsistencies or potential issues.
Run the ESLint linter and see the reported problems.
Run the Prettier formatter and observe how it automatically adjusts your code style.
6. Debugging, Chrome DevTools
The browser's developer tools are invaluable for debugging JavaScript. Chrome DevTools is particularly powerful.

Key Features for JavaScript Debugging:

Sources Panel: Allows you to view your project's source files, set breakpoints, step through code, and inspect variables.
Console Panel: Displays logs, errors, and allows you to execute JavaScript expressions in the context of the current page.
Breakpoints: You can set breakpoints in your code (either in the Sources panel or by using the debugger; statement) to pause execution and inspect the current state.
Watch Expressions: You can add variables or expressions to the Watch panel to monitor their values as you step through your code.
Call Stack: Shows the sequence of function calls that led to the current point of execution.
Scope: Displays the values of variables in the current and enclosing scopes.
Example:

JavaScript

function calculateSum(a, b) {
  let result = a + b;
  debugger; // Execution will pause here in DevTools
  result = result * 2;
  console.log('The result is:', result);
  return result;
}

calculateSum(5, 10);
Open your HTML page in Chrome, open DevTools (usually by pressing F12), go to the Sources panel, find your script, and you'll see the debugger; statement has paused the execution. You can then step over the next line, step into functions, inspect the result, a, and b variables, and see the call stack.

Practice Assignment 6:

Write a JavaScript function with a bug (e.g., an off-by-one error in a loop).
Create an HTML file that calls this function and displays the result.
Use Chrome DevTools to debug your JavaScript code. Set breakpoints, step through the execution, and inspect variables to identify and fix the bug.
7. TDD with Jest
Test-Driven Development (TDD) is a development approach where you write tests before you write the actual code. Jest is a popular JavaScript testing framework, especially known for its ease of use and built-in features.

Install Jest as a dev dependency:

Bash

npm install --save-dev jest
# or
yarn add --dev jest
Add a test script to your package.json:

JSON

"scripts": {
  "test": "jest"
}
Create a test file. Jest typically looks for files with the .test.js or .spec.js extension, often in a __tests__ directory. For example, if you have a file math.js, your test file might be __tests__/math.test.js.
JavaScript

// math.js
function add(a, b) {
  return a + b;
}

module.exports = { add };
JavaScript

// __tests__/math.test.js
const { add } = require('../math');

describe('add', () => {
  test('should return the sum of two numbers

  ---
# 🚦 MODULE 5: Data Structures, Algorithms & Patterns
  ---
  ## 🔢 1. Arrays, Stacks, Queues, Linked Lists

 📚 Concepts

Arrays: Fixed-size, index-based data structure.

Stacks (LIFO): push, pop — used in backtracking, expression evaluation.

Queues (FIFO): enqueue, dequeue — used in BFS, task scheduling.

Linked Lists: Nodes linked via pointers — singly, doubly.

## 💡 Examples (JavaScript)

// Stack
class Stack {
  constructor() { this.stack = []; }
  push(val) { this.stack.push(val); }
  pop() { return this.stack.pop(); }
}

// Queue
class Queue {
  constructor() { this.queue = []; }
  enqueue(val) { this.queue.push(val); }
  dequeue() { return this.queue.shift(); }
}

## 🧠 Practice

Implement a circular queue.

Reverse a linked list iteratively and recursively.

Use a stack to check for balanced parentheses.

## 🔁 2. Recursion, Sorting & Searching

📚 Concepts

Recursion: Function calls itself.

Sorting: Bubble, Selection, Insertion, Merge, Quick.

Searching: Linear, Binary (sorted array).

## 💡 Examples

// Recursive factorial
function factorial(n) {
  if (n <= 1) return 1;
  return n * factorial(n - 1);
}

// Binary search
function binarySearch(arr, target) {
  let low = 0, high = arr.length - 1;
  while (low <= high) {
    const mid = Math.floor((low + high) / 2);
    if (arr[mid] === target) return mid;
    arr[mid] < target ? low = mid + 1 : high = mid - 1;
  }
  return -1;
}

🧠 Practice

Implement merge sort and quicksort.

Use recursion to generate Fibonacci numbers.

Implement binary search on a rotated array.

## 📏 3. Big-O Notation

📚 Concepts

Measures algorithm efficiency.

Common complexities:

Constant: O(1)

Linear: O(n)

Logarithmic: O(log n)

Quadratic: O(n^2)

Exponential: O(2^n)

💡 Examples

// O(n)
function sumArray(arr) {
  return arr.reduce((acc, val) => acc + val, 0);
}

// O(1)
function getFirst(arr) {
  return arr[0];
}

🧠 Practice

Analyze time complexity of your previous sorting algorithms.

Compare different searching techniques using Big-O.

## 🧩 4. Design Patterns: Module, Observer, Factory, Singleton

📚 Concepts

Module: Encapsulation with closures.

Observer: Subscribe/notify.

Factory: Creates objects without exposing instantiation logic.

Singleton: Single instance throughout app.

💡 Examples

// Singleton
const Singleton = (function() {
  let instance;
  function createInstance() {
    return { value: Math.random() };
  }
  return {
    getInstance() {
      if (!instance) instance = createInstance();
      return instance;
    }
  };
})();

🧠 Practice
---
Create a notification system using the Observer pattern.

Use a factory to create different types of users.

Convert an IIFE into a Module pattern.

## 🔬 5. Functional Programming in JS

📚 Concepts

Pure functions, immutability, first-class functions

map, filter, reduce

💡 Examples

const numbers = [1, 2, 3, 4, 5];
const squares = numbers.map(x => x * x);
const evens = numbers.filter(x => x % 2 === 0);
const sum = numbers.reduce((a, b) => a + b, 0);

🧠 Practice

Create a pure function to flatten nested arrays.

Use reduce to group elements.

Refactor imperative code into functional code.

## ⚙️ 6. State Machines with XState

📚 Concepts
---
Declarative state management

States, events, transitions

Visualize with https://stately.ai

## 💡 Example

import { createMachine, interpret } from 'xstate';

const toggleMachine = createMachine({
  id: 'toggle',
  initial: 'inactive',
  states: {
    inactive: { on: { TOGGLE: 'active' } },
    active: { on: { TOGGLE: 'inactive' } }
  }
});

const service = interpret(toggleMachine).start();
service.send('TOGGLE');

## 🧠 Practice

Model a login/logout flow.

Create a state machine for a traffic light.

Use XState with React to manage UI state.

🛠️ Project: Code Interview Prep Kit

## 🎯 Objective

Build a repository of 10+ custom implementations of key data structures and algorithms.

✅ Checklist
---
# 🌍 MODULE 6: Advanced Concepts & Real-World Integration
---
👨‍💻 1. Object-Oriented Programming in JavaScript

📚 Concepts

Classes & Constructors

Prototypes & Prototype Chain

Inheritance (ES5 & ES6)

💡 Examples

class Person {
  constructor(name) {
    this.name = name;
  }
  greet() {
    return `Hello, I'm ${this.name}`;
  }
}

class Student extends Person {
  constructor(name, grade) {
    super(name);
    this.grade = grade;
  }
  info() {
    return `${this.name} is in grade ${this.grade}`;
  }
}

🧠 Practice

Create a Vehicle base class and extend it with Car and Bike.

Implement a method override in a subclass.

Create a custom prototype object and link it manually using Object.create().

🔄 2. Reactive Programming with RxJS

📚 Concepts

Observables, Observers, Subscriptions

Operators: map, filter, merge, combineLatest, switchMap

💡 Example

import { fromEvent } from 'rxjs';
import { map } from 'rxjs/operators';

fromEvent(document, 'click')
  .pipe(map(event => `Click at ${event.clientX}, ${event.clientY}`))
  .subscribe(console.log);

🧠 Practice

Create an input field with debounced live search using RxJS.

Use combineLatest to combine values from two input fields.

Use interval and take to build a countdown timer.

🧱 3. Web Components

📚 Concepts

Custom Elements

Shadow DOM

HTML Templates

💡 Example

class MyCard extends HTMLElement {
  constructor() {
    super();
    const shadow = this.attachShadow({ mode: 'open' });
    shadow.innerHTML = `
      <style>div { padding: 1em; border: 1px solid #ccc; }</style>
      <div><slot></slot></div>
    `;
  }
}
customElements.define('my-card', MyCard);

🧠 Practice

Create a user-avatar component.

Build a modal-dialog using Shadow DOM.

Use slots for flexible templating.

🛰️ 4. Service Workers & PWA Concepts

📚 Concepts

Service Worker lifecycle: install, activate, fetch

Caching strategies

Manifest.json

Offline-first & push notifications

💡 Example

self.addEventListener('install', event => {
  event.waitUntil(
    caches.open('v1').then(cache => cache.add('/index.html'))
  );
});

self.addEventListener('fetch', event => {
  event.respondWith(
    caches.match(event.request).then(response => response || fetch(event.request))
  );
});

🧠 Practice

Build a cache-first image gallery.

Register a service worker and log fetch events.

Create a manifest.json and make your site installable.

🛡️ 5. Security: XSS, CSP, JWT

📚 Concepts

XSS: Cross-site scripting, sanitize input

CSP: Content Security Policy

JWT: JSON Web Tokens for stateless auth

💡 Examples

// Basic JWT usage
const token = jwt.sign({ userId: 123 }, 'secret', { expiresIn: '1h' });
jwt.verify(token, 'secret');

🧠 Practice

Simulate an XSS attack and fix it with input sanitization.

Set a basic CSP header.

Implement a login flow using JWT (encode/decode on frontend).

📡 6. Working with WebSockets

📚 Concepts

Real-time data communication

WebSocket API: new WebSocket(), onmessage, send

💡 Example

const socket = new WebSocket('ws://localhost:8080');
socket.onopen = () => socket.send('Hello Server!');
socket.onmessage = e => console.log('Message:', e.data);

🧠 Practice

Connect to a public WebSocket echo server.

Build a simple real-time chat with ws in Node.js.

Broadcast a message to multiple clients.

🔡 7. TypeScript Introduction

📚 Concepts

Type annotations, interfaces, enums

Classes and generics

Type checking and tooling

💡 Example

function greet(name: string): string {
  return `Hello, ${name}`;
}

interface User {
  id: number;
  username: string;
}

const user: User = { id: 1, username: 'alice' };

🧠 Practice

Convert a JS file to TypeScript.

Define interfaces for API response objects.

Create a generic function to reverse an array.

🏁 Capstone Project: Full-Feature JS App

🎯 Objective

Build a complete, framework-free JavaScript application:

Options:

Realtime Chat App (WebSocket, RxJS, OOP)

E-commerce SPA (Routing, Local Storage, Web Components)

✅ Requirements

Modular OOP-based architecture

TypeScript types (optional but encouraged)

Web Components for UI

RxJS for streams/state

Service Workers for offline support

JWT authentication mock (optional)

Deployment-ready with PWA features

💼 Deliverables

Fully working app (hosted or demoable)

Codebase on GitHub

README with architecture and features



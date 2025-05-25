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

# Module 3: DOM Manipulation & Browser APIs
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

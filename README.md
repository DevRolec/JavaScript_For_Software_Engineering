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

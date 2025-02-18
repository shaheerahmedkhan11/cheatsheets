# JavaScript Cheat Sheet

## Basics

### Variables
```javascript
var name = "John"; // Function-scoped
let age = 30; // Block-scoped
const isStudent = true; // Block-scoped, constant
```

### Data Types
- String
- Number
- Boolean
- Object
- Array
- Undefined
- Null
- Symbol (ES6)
- BigInt (ES11)

### Operators
- Arithmetic: `+`, `-`, `*`, `/`, `%`
- Assignment: `=`, `+=`, `-=`, `*=`, `/=`
- Comparison: `==`, `===`, `!=`, `!==`, `>`, `<`, `>=`, `<=`
- Logical: `&&`, `||`, `!`
- Ternary: `condition ? expr1 : expr2`

### Functions
```javascript
// Function Declaration
function greet(name) {
  return `Hello, ${name}!`;
}

// Function Expression
const greet = function(name) {
  return `Hello, ${name}!`;
};

// Arrow Function
const greet = (name) => `Hello, ${name}!`;
```

## Control Structures

### Conditional Statements
```javascript
if (condition) {
  // code
} else if (anotherCondition) {
  // code
} else {
  // code
}
```

### Switch Statement
```javascript
switch (expression) {
  case value1:
    // code
    break;
  case value2:
    // code
    break;
  default:
    // code
}
```

### Loops
```javascript
// For Loop
for (let i = 0; i < 5; i++) {
  // code
}

// While Loop
let i = 0;
while (i < 5) {
  // code
  i++;
}

// Do-While Loop
let i = 0;
do {
  // code
  i++;
} while (i < 5);

// For-Of Loop (ES6)
for (const element of array) {
  // code
}

// For-In Loop
for (const key in object) {
  // code
}
```

## Objects and Arrays

### Objects
```javascript
const person = {
  name: "John",
  age: 30,
  greet: function() {
    return `Hello, my name is ${this.name}`;
  }
};
```

### Arrays
```javascript
const numbers = [1, 2, 3, 4, 5];

// Array Methods
numbers.push(6); // Adds to end
numbers.pop(); // Removes from end
numbers.shift(); // Removes from start
numbers.unshift(0); // Adds to start
numbers.map(num => num * 2); // [2, 4, 6, 8, 10]
numbers.filter(num => num > 3); // [4, 5]
numbers.reduce((acc, num) => acc + num, 0); // 15
```

## ES6 Features

### Template Literals
```javascript
const name = "John";
const greeting = `Hello, ${name}!`;
```

### Destructuring
```javascript
// Object Destructuring
const { name, age } = person;

// Array Destructuring
const [first, second] = numbers;
```

### Spread and Rest
```javascript
// Spread Operator
const newNumbers = [...numbers, 6, 7, 8];

// Rest Parameters
function sum(...args) {
  return args.reduce((acc, num) => acc + num, 0);
}
```

### Promises
```javascript
const promise = new Promise((resolve, reject) => {
  // async code
  if (success) {
    resolve(result);
  } else {
    reject(error);
  }
});

promise.then(result => {
  // code
}).catch(error => {
  // code
});
```

### Async/Await
```javascript
async function fetchData() {
  try {
    const response = await fetch('url');
    const data = await response.json();
    return data;
  } catch (error) {
    console.error(error);
  }
}
```

## DOM Manipulation

### Selecting Elements
```javascript
const element = document.getElementById('id');
const elements = document.getElementsByClassName('class');
const elements = document.getElementsByTagName('tag');
const element = document.querySelector('.class');
const elements = document.querySelectorAll('.class');
```

### Event Listeners
```javascript
element.addEventListener('click', function(event) {
  // code
});
```

### Modifying Elements
```javascript
element.textContent = 'New Text';
element.innerHTML = '<p>New HTML</p>';
element.style.color = 'blue';
element.classList.add('new-class');
element.setAttribute('name', 'value');
```

## Error Handling
```javascript
try {
  // code
} catch (error) {
  console.error(error);
} finally {
  // code
}
```

## Modules (ES6)
```javascript
// Exporting
export const name = "John";
export function greet() {
  return `Hello, ${name}!`;
}

// Importing
import { name, greet } from './module.js';
```

## Useful Methods

### String Methods
```javascript
const str = 'Hello, World!';
str.length; // 13
str.toUpperCase(); // 'HELLO, WORLD!'
str.toLowerCase(); // 'hello, world!'
str.includes('World'); // true
str.startsWith('Hello'); // true
str.endsWith('!'); // true
str.trim(); // 'Hello, World!'
str.split(', '); // ['Hello', 'World!']
str.replace('World', 'JavaScript'); // 'Hello, JavaScript!'
```

### Number Methods
```javascript
const num = 123.456;
num.toFixed(2); // '123.46'
num.toString(); // '123.456'
Number.isInteger(num); // false
Number.isNaN(num); // false
```

### Array Methods
```javascript
const arr = [1, 2, 3, 4, 5];
arr.length; // 5
arr.concat([6, 7]); // [1, 2, 3, 4, 5, 6, 7]
arr.join(', '); // '1, 2, 3, 4, 5'
arr.slice(1, 3); // [2, 3]
arr.splice(2, 1); // [3], arr is now [1, 2, 4, 5]
arr.indexOf(4); // 2
arr.find(num => num > 3); // 4
arr.findIndex(num => num > 3); // 3
arr.every(num => num > 0); // true
arr.some(num => num > 4); // true
```

## Date and Time
```javascript
const now = new Date();
now.getFullYear(); // 2025
now.getMonth(); // 1 (February)
now.getDate(); // 18
now.getHours(); // 10
now.getMinutes(); // 39
now.getSeconds(); // 17
now.toISOString(); // '2025-02-18T10:39:17.000Z'
```

## JSON
```javascript
const obj = { name: "John", age: 30 };
const jsonString = JSON.stringify(obj); // '{"name":"John","age":30}'
const jsonObj = JSON.parse(jsonString); // { name: "John", age: 30 }
```

## Regular Expressions
```javascript
const regex = /hello/i;
const str = 'Hello, World!';
regex.test(str); // true
str.match(regex); // ['Hello', index: 0, input: 'Hello, World!', groups: undefined]
```
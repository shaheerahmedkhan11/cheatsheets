# JavaScript Lambda Functions Cheatsheet

## Introduction
Lambda functions, also known as arrow functions, are a concise way to write functions in JavaScript. They were introduced in ECMAScript 6 (ES6) and provide a more compact syntax compared to traditional function expressions.

## Syntax
The basic syntax of an arrow function is:
```javascript
(param1, param2, ..., paramN) => { 
  // function body
}
```

### Single Parameter
If there is only one parameter, parentheses can be omitted:
```javascript
param => {
  // function body
}
```

### No Parameters
If there are no parameters, parentheses are required:
```javascript
() => {
  // function body
}
```

### Single Expression
If the function body has only one expression, the curly braces and `return` keyword can be omitted:
```javascript
(param1, param2) => expression
```
This is equivalent to:
```javascript
(param1, param2) => { return expression; }
```

## Examples

### Basic Examples
#### Example 1: No Parameters
```javascript
const sayHello = () => {
  console.log('Hello!');
};
sayHello(); // Output: Hello!
```

#### Example 2: Single Parameter
```javascript
const greet = name => {
  console.log(`Hello, ${name}!`);
};
greet('Alice'); // Output: Hello, Alice!
```

#### Example 3: Multiple Parameters
```javascript
const add = (a, b) => {
  return a + b;
};
console.log(add(3, 4)); // Output: 7
```

### Inline Return
#### Example 4: Inline Return
```javascript
const multiply = (a, b) => a * b;
console.log(multiply(2, 5)); // Output: 10
```

## Advanced Features

### Lexical `this`
Arrow functions do not have their own `this` context; they inherit `this` from the parent scope. This makes them particularly useful for callbacks.

#### Example 5: Lexical `this`
```javascript
function Person() {
  this.age = 0;

  setInterval(() => {
    this.age++;
    console.log(this.age);
  }, 1000);
}

const person = new Person();
// Outputs: 1, 2, 3, 4, ...
```

### No `arguments` Object
Arrow functions do not have their own `arguments` object.

#### Example 6: Spread Operator Instead
```javascript
const sum = (...args) => {
  return args.reduce((acc, curr) => acc + curr, 0);
};
console.log(sum(1, 2, 3, 4)); // Output: 10
```

### Cannot be used as constructors
Arrow functions cannot be used as constructors and will throw an error if used with `new`.

#### Example 7: Constructor Error
```javascript
const Foo = () => {};
const bar = new Foo(); // TypeError: Foo is not a constructor
```

### No `prototype` Property
Arrow functions do not have a `prototype` property.

## Common Use Cases

### Array Methods
Arrow functions are commonly used with array methods like `map`, `filter`, and `reduce`.

#### Example 8: Array Methods
```javascript
const numbers = [1, 2, 3, 4, 5];

// Using map
const squares = numbers.map(n => n * n);
console.log(squares); // Output: [1, 4, 9, 16, 25]

// Using filter
const evenNumbers = numbers.filter(n => n % 2 === 0);
console.log(evenNumbers); // Output: [2, 4]

// Using reduce
const sum = numbers.reduce((acc, n) => acc + n, 0);
console.log(sum); // Output: 15
```

### Event Handlers
Arrow functions are often used as event handlers because of their lexical `this`.

#### Example 9: Event Handlers
```javascript
const button = document.querySelector('button');
button.addEventListener('click', () => {
  console.log('Button clicked!');
});
```

### Shorter Function Syntax
Arrow functions provide a shorter syntax for writing small functions.

#### Example 10: Shorter Syntax
```javascript
// Traditional function expression
const double = function(x) {
  return x * 2;
};

// Arrow function
const double = x => x * 2;
```

## Conclusion
Arrow functions provide a concise and readable way to write functions in JavaScript. They are especially useful for writing small inline functions, callbacks, and functions that maintain the `this` context from their surrounding scope.

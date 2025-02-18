# JavaScript Functions and Classes Cheatsheet

## Functions

### Function Declaration
```javascript
function functionName(parameters) {
  // function body
  return value;
}
```

### Function Expression
```javascript
const functionName = function(parameters) {
  // function body
  return value;
};
```

### Arrow Function
```javascript
const functionName = (parameters) => {
  // function body
  return value;
};
```

### Immediately Invoked Function Expression (IIFE)
```javascript
(function() {
  // function body
})();
```

### Default Parameters
```javascript
function functionName(param1 = defaultValue1, param2 = defaultValue2) {
  // function body
}
```

### Rest Parameters
```javascript
function functionName(...restParams) {
  // function body
}
```

### Function with Callback
```javascript
function functionName(callback) {
  // function body
  callback();
}
```

## Classes

### Class Declaration
```javascript
class ClassName {
  constructor(parameters) {
    // constructor body
  }

  methodName(parameters) {
    // method body
  }

  static staticMethodName(parameters) {
    // static method body
  }
}
```

### Class Expression
```javascript
const ClassName = class {
  constructor(parameters) {
    // constructor body
  }

  methodName(parameters) {
    // method body
  }

  static staticMethodName(parameters) {
    // static method body
  }
};
```

### Inheritance
```javascript
class ParentClass {
  constructor(parameters) {
    // constructor body
  }

  parentMethod(parameters) {
    // method body
  }
}

class ChildClass extends ParentClass {
  constructor(parameters) {
    super(parameters);
    // additional constructor body
  }

  childMethod(parameters) {
    // method body
  }
}
```

### Getters and Setters
```javascript
class ClassName {
  constructor(parameters) {
    this._property = parameters;
  }

  get property() {
    return this._property;
  }

  set property(value) {
    this._property = value;
  }
}
```

### Private Fields and Methods (ES2022)
```javascript
class ClassName {
  #privateField;

  constructor(parameters) {
    this.#privateField = parameters;
  }

  #privateMethod() {
    // private method body
  }

  publicMethod() {
    this.#privateMethod();
  }
}
```

### Static Properties and Methods
```javascript
class ClassName {
  static staticProperty = 'value';

  static staticMethod() {
    // static method body
  }
}
```

### Abstract Class (Using new.target)
```javascript
class AbstractClass {
  constructor() {
    if (new.target === AbstractClass) {
      throw new TypeError("Cannot construct AbstractClass instances directly");
    }
  }

  abstractMethod() {
    throw new Error("Abstract method must be implemented");
  }
}

class ConcreteClass extends AbstractClass {
  constructor() {
    super();
  }

  abstractMethod() {
    // implementation of abstract method
  }
}
```
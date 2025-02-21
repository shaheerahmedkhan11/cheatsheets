# Python Cheat Sheet

## Basics

### Variables and Data Types
```python
x = 5                  # Integer
y = 2.5                # Float
name = "John"          # String
is_student = True      # Boolean
```

### Data Structures
#### Lists
```python
numbers = [1, 2, 3, 4, 5]
numbers.append(6)      # Add to the end
numbers.pop()          # Remove from the end
```

#### Tuples
```python
person = ("John", 25, "Engineer")
```

#### Dictionaries
```python
student = {"name": "John", "age": 25, "course": "Engineering"}
print(student["name"])
```

#### Sets
```python
fruits = {"apple", "banana", "cherry"}
fruits.add("orange")
```

## Control Flow

### Conditional Statements
```python
if x > 0:
    print("Positive")
elif x == 0:
    print("Zero")
else:
    print("Negative")
```

### Loops
#### For Loop
```python
for i in range(5):
    print(i)
```

#### While Loop
```python
count = 0
while count < 5:
    print(count)
    count += 1
```

## Functions
```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Alice"))
```

## Classes and Objects
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        return f"Hello, my name is {self.name} and I am {self.age} years old."

john = Person("John", 25)
print(john.greet())
```

## Modules and Packages
### Importing Modules
```python
import math
print(math.sqrt(16))
```

### Importing Specific Functions
```python
from math import sqrt
print(sqrt(25))
```

## File Handling
```python
# Writing to a file
with open("example.txt", "w") as file:
    file.write("Hello, World!")

# Reading from a file
with open("example.txt", "r") as file:
    content = file.read()
    print(content)
```

## Exception Handling
```python
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")
finally:
    print("Operation complete.")
```

## Libraries and Frameworks

### NumPy
```python
import numpy as np
arr = np.array([1, 2, 3, 4, 5])
print(arr.mean())
```

### Pandas
```python
import pandas as pd
data = {"name": ["John", "Anna"], "age": [25, 30]}
df = pd.DataFrame(data)
print(df)
```

### Matplotlib
```python
import matplotlib.pyplot as plt
plt.plot([1, 2, 3], [4, 5, 6])
plt.show()
```

### Flask (Web Framework)
```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return "Hello, Flask!"

if __name__ == "__main__":
    app.run(debug=True)
```

### Django (Web Framework)
```python
# Install Django using pip: pip install django
# Create a project: django-admin startproject mysite
# Create an app: python manage.py startapp myapp
```

## Useful Built-in Functions
```python
len("hello")            # Length of a string
str(123)                # Convert to string
int("123")              # Convert to integer
type(123)               # Get the type of a variable
```

## List Comprehensions
```python
squares = [x**2 for x in range(10)]
```

## Lambda Functions
```python
add = lambda a, b: a + b
print(add(2, 3))
```

## Map, Filter, Reduce
```python
# Map
nums = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x**2, nums))

# Filter
evens = list(filter(lambda x: x % 2 == 0, nums))

# Reduce
from functools import reduce
sum = reduce(lambda a, b: a + b, nums)
```

## Decorators
```python
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

@my_decorator
def say_hello():
    print("Hello!")

say_hello()
```

## Generators
```python
def my_generator():
    yield 1
    yield 2
    yield 3

gen = my_generator()
for value in gen:
    print(value)
```

## Context Managers
```python
with open("example.txt", "w") as file:
    file.write("Hello, World!")
```

## Virtual Environments
```bash
# Create a virtual environment
python -m venv myenv

# Activate the virtual environment
# On Windows
myenv\Scripts\activate
# On Unix or MacOS
source myenv/bin/activate

# Deactivate the virtual environment
deactivate
```

## Commonly Used Packages
- **requests**: For making HTTP requests
- **beautifulsoup4**: For web scraping
- **scikit-learn**: For machine learning
- **tensorflow**: For deep learning
- **pytorch**: For deep learning

## Tips and Tricks
- Use `help()` and `dir()` to explore objects and modules.
- Use list slicing: `my_list[start:end:step]`
- Use `_` as a variable name for unused variables in loops.
- Use `enumerate()` to get the index and value in a loop.
- Use `zip()` to iterate over multiple sequences in parallel.
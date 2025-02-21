# C++ Comprehensive Cheatsheet for Beginners

## Table of Contents
1. [Introduction](#introduction)
2. [Basic Syntax](#basic-syntax)
3. [Variables and Data Types](#variables-and-data-types)
4. [Operators](#operators)
5. [Control Structures](#control-structures)
6. [Functions](#functions)
7. [Arrays and Strings](#arrays-and-strings)
8. [Pointers](#pointers)
9. [Structures](#structures)
10. [Classes and Objects](#classes-and-objects)
11. [Inheritance](#inheritance)
12. [Polymorphism](#polymorphism)
13. [Standard Template Library (STL)](#standard-template-library-stl)
14. [File I/O](#file-io)
15. [Common Standard Library Functions](#common-standard-library-functions)

## Introduction
C++ is a general-purpose programming language created by Bjarne Stroustrup as an extension of the C programming language. It is known for its performance, efficiency, and flexibility, making it a popular choice for system/software development and game programming.

## Basic Syntax

```cpp
#include <iostream>  // Preprocessor directive

int main() {         // Main function
    std::cout << "Hello, World!";  // Output to console
    return 0;        // Return statement
}
```

## Variables and Data Types

```cpp
int myNum = 5;               // Integer (whole number)
float myFloat = 5.99;        // Floating point number
char myLetter = 'D';         // Character
bool myBoolean = true;       // Boolean
std::string myText = "Hello"; // String
```

## Operators

### Arithmetic Operators
```cpp
int sum = 5 + 3;     // Addition
int diff = 5 - 3;    // Subtraction
int prod = 5 * 3;    // Multiplication
int quotient = 5 / 3;// Division
int remainder = 5 % 3;// Modulus
```

### Comparison Operators
```cpp
bool isEqual = (5 == 3);     // Equal to
bool isNotEqual = (5 != 3);  // Not equal to
bool isGreater = (5 > 3);    // Greater than
bool isLess = (5 < 3);       // Less than
bool isGreaterEqual = (5 >= 3); // Greater than or equal to
bool isLessEqual = (5 <= 3);    // Less than or equal to
```

### Logical Operators
```cpp
bool andOp = (5 > 3 && 3 < 5); // Logical AND
bool orOp = (5 > 3 || 3 > 5);  // Logical OR
bool notOp = !(5 > 3);         // Logical NOT
```

## Control Structures

### If-Else
```cpp
if (condition) {
    // code to be executed if condition is true
} else {
    // code to be executed if condition is false
}
```

### Switch
```cpp
switch (expression) {
    case value1:
        // code to be executed if expression equals value1
        break;
    case value2:
        // code to be executed if expression equals value2
        break;
    default:
        // code to be executed if expression doesn't match any case
}
```

### Loops

#### For Loop
```cpp
for (int i = 0; i < 5; i++) {
    // code to be executed
}
```

#### While Loop
```cpp
while (condition) {
    // code to be executed
}
```

#### Do-While Loop
```cpp
do {
    // code to be executed
} while (condition);
```

## Functions

```cpp
returnType functionName(parameters) {
    // function body
}
```

Example:
```cpp
int add(int a, int b) {
    return a + b;
}
```

## Arrays and Strings

### Arrays
```cpp
int myArray[5] = {1, 2, 3, 4, 5};
```

### Strings
```cpp
std::string myString = "Hello";
```

## Pointers

```cpp
int var = 20;
int *ptr = &var;
```

## Structures

```cpp
struct Person {
    std::string name;
    int age;
};
```

## Classes and Objects

```cpp
class MyClass {
public:
    int myNum;
    std::string myString;
};

int main() {
    MyClass myObj;
    myObj.myNum = 15;
    myObj.myString = "Hello";
    return 0;
}
```

## Inheritance

```cpp
class Base {
public:
    void display() {
        std::cout << "Base class display function";
    }
};

class Derived : public Base {
};
```

## Polymorphism

### Function Overloading
```cpp
int add(int a, int b) {
    return a + b;
}

double add(double a, double b) {
    return a + b;
}
```

### Function Overriding
```cpp
class Base {
public:
    virtual void display() {
        std::cout << "Base class display function";
    }
};

class Derived : public Base {
public:
    void display() override {
        std::cout << "Derived class display function";
    }
};
```

## Standard Template Library (STL)

### Vectors
```cpp
#include <vector>
std::vector<int> myVector = {1, 2, 3, 4, 5};
```

### Maps
```cpp
#include <map>
std::map<int, std::string> myMap;
myMap[1] = "One";
myMap[2] = "Two";
```

## File I/O

### Writing to a File
```cpp
#include <fstream>
std::ofstream myfile("example.txt");
if (myfile.is_open()) {
    myfile << "Writing to file.\n";
    myfile.close();
}
```

### Reading from a File
```cpp
#include <fstream>
std::string line;
std::ifstream myfile("example.txt");
if (myfile.is_open()) {
    while (getline(myfile, line)) {
        std::cout << line << '\n';
    }
    myfile.close();
}
```

## Common Standard Library Functions

### Math Functions
```cpp
#include <cmath>
double squareRoot = sqrt(16);  // Square root
double power = pow(2, 3);      // Power
```

### String Functions
```cpp
#include <string>
std::string str = "Hello";
int len = str.length();        // String length
std::string substr = str.substr(0, 2); // Substring
```

### Algorithm Functions
```cpp
#include <algorithm>
std::vector<int> v = {4, 2, 3, 1};
std::sort(v.begin(), v.end()); // Sort
std::reverse(v.begin(), v.end()); // Reverse
```

This cheatsheet covers the basics of C++ and should serve as a quick reference guide for beginners. For more detailed explanations and advanced topics, refer to C++ documentation and other learning resources.
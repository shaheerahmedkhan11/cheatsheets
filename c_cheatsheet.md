# C Programming Cheatsheet

## Basics

### Structure of a C Program
```c
#include <stdio.h>

int main() {
    // Your code here
    return 0;
}
```

### Data Types
- `int`: Integer
- `float`: Floating point number
- `double`: Double precision floating point number
- `char`: Character
- `void`: Empty

### Variables
```c
int a = 10;
float b = 5.5;
char c = 'A';
```

### Constants
```c
#define PI 3.14
const int DAYS_IN_WEEK = 7;
```

## Control Structures

### Conditional Statements
```c
if (condition) {
    // code to be executed if condition is true
} else {
    // code to be executed if condition is false
}
```

### Switch Case
```c
switch (variable) {
    case value1:
        // code to be executed if variable == value1
        break;
    case value2:
        // code to be executed if variable == value2
        break;
    default:
        // code to be executed if variable doesn't match any case
}
```

### Loops
#### For Loop
```c
for (initialization; condition; increment) {
    // code to be executed
}
```

#### While Loop
```c
while (condition) {
    // code to be executed
}
```

#### Do-While Loop
```c
do {
    // code to be executed
} while (condition);
```

## Functions

### Function Declaration and Definition
```c
returnType functionName(parameters) {
    // function body
}
```

### Example
```c
int add(int a, int b) {
    return a + b;
}
```

### Calling a Function
```c
int result = add(5, 3);
```

## Arrays
```c
int numbers[5] = {1, 2, 3, 4, 5};
char name[] = "John";
```

## Pointers
```c
int a = 10;
int *p = &a;
```

## Strings
```c
char str[20] = "Hello, World!";
```

## Input and Output

### Standard Input and Output
```c
#include <stdio.h>

int main() {
    int a;
    printf("Enter a number: ");
    scanf("%d", &a);
    printf("You entered: %d\n", a);
    return 0;
}
```

## File I/O

### Reading from a File
```c
FILE *file;
file = fopen("filename.txt", "r");
if (file) {
    // read from file
    fclose(file);
}
```

### Writing to a File
```c
FILE *file;
file = fopen("filename.txt", "w");
if (file) {
    // write to file
    fclose(file);
}
```

## Memory Management

### Dynamic Memory Allocation
```c
#include <stdlib.h>

int *p = (int *)malloc(sizeof(int) * 5);
if (p != NULL) {
    // use allocated memory
    free(p);
}
```

## Common Functions

### String Functions
- `strlen(str)`: Returns the length of the string
- `strcpy(dest, src)`: Copies string src to dest
- `strcat(dest, src)`: Concatenates string src to the end of dest
- `strcmp(str1, str2)`: Compares two strings

### Math Functions
- `pow(base, exp)`: Returns base raised to the power exp
- `sqrt(x)`: Returns the square root of x
- `abs(x)`: Returns the absolute value of x

## Preprocessor Directives

### Including Files
```c
#include <stdio.h>
#include "myheader.h"
```

### Macros
Macros are a way to define constant values or functions that get expanded by the preprocessor before compilation.

#### Defining Macros
```c
#define NAME value
```
Example:
```c
#define PI 3.14159
#define MAX_SIZE 100
```

#### Using Macros
```c
int radius = 5;
float area = PI * radius * radius;
```

#### Function-like Macros
You can define macros that work like functions but are expanded inline.
```c
#define SQUARE(x) ((x) * (x))
```
Example:
```c
int num = 4;
int result = SQUARE(num); // Expands to (4 * 4)
```

#### Conditional Compilation
You can conditionally include or exclude parts of the code using macros.
```c
#ifdef DEBUG
    // Debug-specific code
#endif

#ifndef HEADER_FILE
#define HEADER_FILE
    // Header file content
#endif

#if CONDITION
    // Code to include if CONDITION is true
#else
    // Code to include if CONDITION is false
#endif
```

### Conditional Compilation Example
```c
#define DEBUG

int main() {
    #ifdef DEBUG
        printf("Debug mode is enabled\n");
    #endif

    printf("This is a C program\n");
    return 0;
}
```

## Structs
Structures (structs) are user-defined data types that allow grouping variables of different types.
```c
struct Person {
    char name[50];
    int age;
    float salary;
};
```
Example:
```c
struct Person person1;

strcpy(person1.name, "John");
person1.age = 30;
person1.salary = 55000.50;
```

### Accessing Members
```c
printf("Name: %s\n", person1.name);
printf("Age: %d\n", person1.age);
printf("Salary: %.2f\n", person1.salary);
```

## Multifile Compilation

### Header File (`myheader.h`)
```c
#ifndef MYHEADER_H
#define MYHEADER_H

void printMessage();

#endif
```

### Source File (`myheader.c`)
```c
#include <stdio.h>
#include "myheader.h"

void printMessage() {
    printf("Hello from another file!\n");
}
```

### Main File (`main.c`)
```c
#include "myheader.h"

int main() {
    printMessage();
    return 0;
}
```

### Compilation
To compile multiple files, use the following command:
```sh
gcc main.c myheader.c -o myprogram
```

## Windows Programming

### Setting Up a Windows Project
1. Ensure you have a C compiler installed like MinGW.
2. Create a new project directory.

### Simple Windows Application

#### Header File (`winapp.h`)
```c
#ifndef WINAPP_H
#define WINAPP_H

#include <windows.h>

// Function prototypes
LRESULT CALLBACK WindowProc(HWND hwnd, UINT uMsg, WPARAM wParam, LPARAM lParam);
int WINAPI wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, PWSTR pCmdLine, int nCmdShow);

#endif
```

#### Source File (`winapp.c`)
```c
#include "winapp.h"

// Window Procedure function
LRESULT CALLBACK WindowProc(HWND hwnd, UINT uMsg, WPARAM wParam, LPARAM lParam) {
    switch (uMsg) {
        case WM_DESTROY:
            PostQuitMessage(0);
            return 0;
        case WM_PAINT: {
            PAINTSTRUCT ps;
            HDC hdc = BeginPaint(hwnd, &ps);
            FillRect(hdc, &ps.rcPaint, (HBRUSH)(COLOR_WINDOW + 1));
            EndPaint(hwnd, &ps);
        }
        return 0;
    }
    return DefWindowProc(hwnd, uMsg, wParam, lParam);
}

// Main function
int WINAPI wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, PWSTR pCmdLine, int nCmdShow) {
    const wchar_t CLASS_NAME[] = L"Sample Window Class";

    WNDCLASS wc = { };

    wc.lpfnWndProc = WindowProc;
    wc.hInstance = hInstance;
    wc.lpszClassName = CLASS_NAME;

    RegisterClass(&wc);

    HWND hwnd = CreateWindowEx(
        0,
        CLASS_NAME,
        L"Learn to Program Windows",
        WS_OVERLAPPEDWINDOW,
        CW_USEDEFAULT, CW_USEDEFAULT, CW_USEDEFAULT, CW_USEDEFAULT,
        NULL,
        NULL,
        hInstance,
        NULL
    );

    if (hwnd == NULL) {
        return 0;
    }

    ShowWindow(hwnd, nCmdShow);

    MSG msg = { };
    while (GetMessage(&msg, NULL, 0, 0)) {
        TranslateMessage(&msg);
        DispatchMessage(&msg);
    }

    return 0;
}
```

### Compilation
To compile the Windows application, use the following command:
```sh
gcc winapp.c -o winapp -lgdi32
```

### Running the Program
After compilation, run the executable `winapp.exe`. You should see a simple window created by your application.

## Windows.h Overview

The `windows.h` header file includes declarations for all of the functions in the Windows API, all the common macros used by Windows programmers, and all the data types used by the various functions and subsystems.

### Common Data Types
- `HWND`: Handle to a window.
- `HINSTANCE`: Handle to an instance.
- `HDC`: Handle to a device context.
- `WPARAM`: Message parameter (unsigned 32-bit or 64-bit value).
- `LPARAM`: Message parameter (signed 32-bit or 64-bit value).
- `LRESULT`: Message return value.
- `BOOL`: Boolean value (TRUE or FALSE).
- `DWORD`: 32-bit unsigned integer.
- `LPCTSTR`: Long pointer to a constant string (text).

### Common Functions
- `CreateWindowEx`: Creates an overlapped, pop-up, or child window with an extended window style.
- `DefWindowProc`: Calls the default window procedure to provide default processing for any window messages that an application does not process.
- `DispatchMessage`: Dispatches a message to a window procedure.
- `GetMessage`: Retrieves a message from the calling thread's message queue.
- `RegisterClass`: Registers a window class for subsequent use in calls to the `CreateWindow` function.
- `ShowWindow`: Sets the specified window's show state.
- `TranslateMessage`: Translates virtual-key messages into character messages.
- `UpdateWindow`: Updates the client area of the specified window by sending a `WM_PAINT` message if the window's update region is not empty.

### Event Handling
Windows programming heavily relies on event-driven programming. The primary mechanism for handling events is through the Window Procedure (`WindowProc`), which handles messages sent to a window.

### Sample WindowProc Function
```c
LRESULT CALLBACK WindowProc(HWND hwnd, UINT uMsg, WPARAM wParam, LPARAM lParam) {
    switch (uMsg) {
        case WM_DESTROY:
            PostQuitMessage(0);
            return 0;
        case WM_PAINT: {
            PAINTSTRUCT ps;
            HDC hdc = BeginPaint(hwnd, &ps);
            FillRect(hdc, &ps.rcPaint, (HBRUSH)(COLOR_WINDOW + 1));
            EndPaint(hwnd, &ps);
        }
        return 0;
    }
    return DefWindowProc(hwnd, uMsg, wParam, lParam);
}
```

### Example of Main Function in Windows Application
```c
int WINAPI wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, PWSTR pCmdLine, int nCmdShow) {
    const wchar_t CLASS_NAME[] = L"Sample Window Class";

    WNDCLASS wc = { };

    wc.lpfnWndProc = WindowProc;
    wc.hInstance = hInstance;
    wc.lpszClassName = CLASS_NAME;

    RegisterClass(&wc);

    HWND hwnd = CreateWindowEx(
        0,
        CLASS_NAME,
        L"Learn to Program Windows",
        WS_OVERLAPPEDWINDOW,
        CW_USEDEFAULT, CW_USEDEFAULT, CW_USEDEFAULT, CW_USEDEFAULT,
        NULL,
        NULL,
        hInstance,
        NULL
    );

    if (hwnd == NULL) {
        return 0;
    }

    ShowWindow(hwnd, nCmdShow);

    MSG msg = { };
    while (GetMessage(&msg, NULL, 0, 0)) {
        TranslateMessage(&msg);
        DispatchMessage(&msg);
    }

    return 0;
}
```

# 6: Functions and Variable Scope in C

## What is a Function?

* A block of code that performs a specific task
* Helps in code reuse and modularity
* Functions reduce repetition in programs

---

# Function Syntax

```c
return_type function_name(parameters) {
    // code
}
```

### Example

```c
int add(int a, int b) {
    return a + b;
}
```

---

# Function Call

* A function executes only when it is called

### Example

```c
printSum(50, 60);
```

---

# Types of Functions

## 1. No Arguments, No Return Value

* Function does not take input
* Function does not return anything

### Example

```c
#include<stdio.h>

void greet() {
    printf("Hey");
}

int main() {
    greet();
    return 0;
}
```

---

## 2. With Arguments, No Return Value

* Function takes input values
* Function does not return anything

### Example

```c
#include<stdio.h>

void greet(char name[]) {
    printf("Hey %s", name);
}

int main() {
    greet("Alice");
    return 0;
}
```

---

## 3. With Arguments, With Return Value

* Function takes input values
* Function returns a value

### Example

```c
#include<stdio.h>

int add(int a, int b) {
    int sum = a + b;
    return sum;
}

int main() {
    int s = add(50, 60);
    printf("%d", s);

    return 0;
}
```

---

## 4. No Arguments, With Return Value

* Function does not take input
* Function returns a value

### Example

```c
#include<stdio.h>

int getSum() {
    return 100;
}

int main() {
    printf("%d", getSum());

    return 0;
}
```

---

# Example Program

```c
#include<stdio.h>

// with arguments, no return value
void greet(char name[]) {
    printf("Hey %s\n", name);
}

// with arguments, with return value
int add(int a, int b) {
    int sum = a + b;
    return sum;
}

// no arguments, return value
int getSum() {
    return 100;
}

// arguments, no return value
void printSum(int a, int b) {
    printf("%d\n", a + b);
}

int main() {

    greet("Alice");

    int s = add(50, 60);
    printf("%d\n", s);

    printf("%d\n", getSum());

    printSum(50, 60);

    return 0;
}
```

---

# Variable Scope in C

## What is Scope?

* Scope defines where a variable can be accessed in a program

---

# Types of Scope

## 1. Global Scope

* Declared outside all functions
* Accessible from any function in the program

### Example

```c
int global_var = 100;
```

---

## 2. Local Scope

* Declared inside a function or block
* Accessible only within that function/block

### Example

```c
int local_var = 10;
```

---

# Scope Example Program

```c
#include <stdio.h>

// Global variable
int global_var = 100;

void myFunction() {

    // Local variable
    int local_var = 10;

    printf("Inside myFunction:\n");
    printf("Local: %d, Global: %d\n", local_var, global_var);
}

int main() {

    myFunction();

    printf("\nInside main:\n");
    printf("Global: %d\n", global_var);

    // This will give error
    // printf("%d", local_var);

    return 0;
}
```

---

# Output

```text
Inside myFunction:
Local: 10, Global: 100

Inside main:
Global: 100
```

---



# Practical Questions – Functions and Variable Scope in C

## 1. Simple Greeting Function

Create a function `greet()` that prints:

```text
Welcome to C Programming
```

---

## 2. Function with Arguments

Create a function `displayName()` that accepts a student name and prints:

```text
Hello <name>
```

Example:

```text
Hello Rahul
```

---

## 3. Addition Using Return Value

Create a function `add()` that accepts two integers and returns their sum.

### Sample Output

```text
Sum = 80
```

---

## 4. Find Square of a Number

Create a function `square()` that accepts a number and returns its square.

### Example

```text
Input: 5
Output: 25
```

---

## 5. Even or Odd Using Function

Write a function `checkEvenOdd()` that takes a number as input and prints whether the number is even or odd.

### Example

```text
Input: 7
Output: Odd
```

---

## 6. Maximum of Two Numbers

Create a function `maxNum()` that accepts two numbers and returns the larger number.

### Example

```text
Input: 10 20
Output: 20
```

---

## 7. Global and Local Variable Demo

Create a program using:

* One global variable
* One local variable

Print both variables inside a function and inside `main()`.

---

## 8. Calculator Using Functions

Create separate functions for:

* Addition
* Subtraction
* Multiplication
* Division

Take two numbers from the user and display all operations.

---

## 9. Factorial Using Function

Create a function `factorial()` that returns the factorial of a number.

### Example

```text
Input: 5
Output: 120
```

---

## 10. Scope Error Observation

Write a program where:

* A variable is declared inside a function
* Try accessing it outside the function

Observe and explain the compiler error related to scope.


---
# Extra Questions

# 1. No Arguments, No Return Value – Practical Questions

## 1.
Create a function `showMessage()` that prints `"Learning C Functions"`.

## 2.
Write a function `printLine()` that prints a line of stars (`**********`) five times.

## 3.
Create a function `showMenu()` that displays:
- 1. Add
- 2. Subtract
- 3. Exit

## 4.
Write a function `collegeName()` that prints your college or institute name.

## 5.
Create a function `evenNumbers()` that prints all even numbers from 1 to 20.

---

# 2. With Arguments, No Return Value – Practical Questions

## 1.
Write a function `greet(char name[])` that prints:
`Hello <name>`

## 2.
Create a function `printSquare(int n)` that prints the square of a number.

## 3.
Write a function `studentInfo(char name[], int age)` that displays student details.

## 4.
Create a function `table(int n)` that prints the multiplication table of a number.

## 5.
Write a function `checkEvenOdd(int n)` that checks whether a number is even or odd and prints the result.

---

# 3. With Arguments, With Return Value – Practical Questions

## 1.
Create a function `add(int a, int b)` that returns the sum of two numbers.

## 2.
Write a function `largest(int a, int b)` that returns the larger number.

## 3.
Create a function `cube(int n)` that returns the cube of a number.

## 4.
Write a function `isPositive(int n)` that returns `1` if positive otherwise `0`.

## 5.
Create a function `areaRectangle(int length, int breadth)` that returns the area of a rectangle.

---

# 4. No Arguments, With Return Value – Practical Questions

## 1.
Create a function `getNumber()` that returns `100`.

## 2.
Write a function `piValue()` that returns `3.14`.

## 3.
Create a function `currentYear()` that returns the current year.

## 4.
Write a function `getEvenNumber()` that returns any even number.

## 5.
Create a function `luckyNumber()` that returns your lucky number and print it in `main()`.

---

# 5. Function Call – Practical Questions

## 1.
Create a function `hello()` and call it three times from `main()`.

## 2.
Write a program where `main()` calls two different functions:
- `showName()`
- `showAge()`

## 3.
Create a calculator program using function calls for addition and subtraction.

## 4.
Write a program where one function calls another function internally.

## 5.
Create a menu-driven program using function calls for:
- Area of Circle
- Area of Rectangle
- Area of Triangle

---

# 6. Global Scope – Practical Questions

## 1.
Create a global variable `companyCode` and print it inside two different functions.

## 2.
Write a program with a global variable `count = 0` and increase it inside multiple functions.

## 3.
Create a global variable `pi = 3.14` and use it to calculate the area of a circle.

## 4.
Write a program where a global variable is modified inside a function and printed in `main()`.

## 5.
Create two functions that access the same global variable `marks`.

---

# 7. Local Scope – Practical Questions

## 1.
Create a local variable inside a function and print it.

## 2.
Write a program where two functions use local variables with the same name but different values.

## 3.
Create a program showing that a local variable cannot be accessed outside its function.

## 4.
Write a program using an `if` block with a local variable inside the block.

## 5.
Create a function `calculate()` with local variables `a` and `b` and print their sum.

---

# 8. Scope-Based Mixed Programs – Practical Questions

## 1.
Create a program using both global and local variables with the same name.

## 2.
Write a program to show the difference between block scope and function scope.

## 3.
Create three functions where each function has its own local variable.

## 4.
Write a program where one function changes a global variable and another function prints it.

## 5.
Create a complete student result program using:
- Global variable for passing marks
- Local variables for student marks
- Functions for calculation and display

---

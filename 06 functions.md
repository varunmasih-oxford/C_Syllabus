# 6: Functions and Variable Scope in C

## What is a Function?

* A block of code that performs a specific task
* Helps in code reuse and modularity
* Functions reduce repetition in programs

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

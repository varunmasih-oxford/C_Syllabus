##  2: Variables, Data Types & Input/Output

### What is a Variable?

* A variable is a **named memory location**
* Used to store data values

### Variable Declaration

```c
int age;
float salary;
char grade;
```

### Data Types in C

| Data Type | Size    | Example |
| --------- | ------- | ------- |
| `int`     | 4 bytes | 10      |
| `float`   | 4 bytes | 10.5    |
| `double`  | 8 bytes | 10.567  |
| `char`    | 1 byte  | 'A'     |

### Variable Initialization

```c
int age = 20;
float marks = 85.5;
char grade = 'A';
```

### Input and Output Functions

* `printf()` → Output
* `scanf()` → Input

### Input/Output Example

```c
#include <stdio.h>

int main() {
    int age;
    printf("Enter your age: ");
    scanf("%d", &age);
    printf("Your age is %d", age);
    return 0;
}
```

### Format Specifiers

| Specifier | Description |
| --------- | ----------- |
| `%d`      | Integer     |
| `%f`      | Float       |
| `%lf`     | Double      |
| `%c`      | Character   |
| `%s`      | String      |

### Common Beginner Mistakes

* Forgetting `&` in `scanf()`
* Using wrong format specifier
* Missing semicolons

### Practice Questions

1. Print your name and age
2. Take two numbers and print their sum
3. Take a character as input and display it
---

# Practical Questions: Variables, Data Types & Input/Output in C

## 1. Basic Input & Output
Write a C program to input an integer and print it.

## 2. Multiple Variables
Write a program to input two integers and display their sum.

## 3. Float Input
Write a program to input a float value (price of a product) and display it with 2 decimal places.

## 4. Character Input
Write a program to input a character and print its ASCII value.

## 5. String Input
Write a program to input a name (string) and print:  
`Hello, <name>`

## 6. Mixed Data Types
Write a program to input:
- an integer (age)  
- a float (height)  
- a character (grade)  

Display all values in one sentence.

## 7. Area of Rectangle
Write a program to input length and width (float) and calculate the area.

## 8. Type Casting
Write a program to input two integers and display their division result as a float.

## 9. Swap Two Numbers
Write a program to input two integers and swap their values (using a third variable).

## 10. Temperature Conversion
Write a program to input temperature in Celsius and convert it to Fahrenheit using:  
`F = (C * 9/5) + 32`

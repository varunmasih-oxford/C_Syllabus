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


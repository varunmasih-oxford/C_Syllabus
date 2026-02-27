# C Programming 

## 1: Introduction to C Programming

### What is C Programming?

* **C** is a **general-purpose, procedural programming language**
* Developed by **Dennis Ritchie (1972)**
* Widely used in:

  * Operating Systems
  * Embedded Systems
  * System Software
  * Compilers

### Why Learn C?

* Foundation for **C++, Java, Python**
* Fast and efficient
* Better understanding of **memory & hardware**
* Popular in **system-level programming**

### Features of C

* Simple and structured
* Portable
* High performance
* Rich library support
* Pointer support

### Structure of a C Program

1. Preprocessor directives
2. `main()` function
3. Statements
4. Return statement

### First C Program

```c
#include <stdio.h>

int main() {
    printf("Hello, World!");
    return 0;
}
```

### Program Explanation

* `#include <stdio.h>` → Input/Output library
* `int main()` → Program execution starts here
* `printf()` → Displays output
* `return 0;` → Ends program successfully

### How to Run a C Program

1. Install **GCC Compiler**
2. Save file as `hello.c`
3. Compile using: `gcc hello.c`
4. Run using: `./a.out`

### Basic Rules of C

* Case-sensitive language
* Each statement ends with `;`
* `main()` function is mandatory

---

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


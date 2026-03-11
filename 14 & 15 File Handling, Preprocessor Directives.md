# 14_File_Handling.md

# File Handling in C

File handling allows programs to **store data permanently in files** instead of keeping it only in RAM.

Files help in:

* Saving program output
* Storing large datasets
* Reading previously stored information

---

# File Pointer

A **file pointer** is used to access and manipulate files.

```c
FILE *fp;
```

`FILE` is a structure defined in the C Standard Library (`stdio.h`).

The pointer `fp` will store the **reference to the opened file**.

---

# Common File Operations

| Operation          | Function               |
| ------------------ | ---------------------- |
| Create / Open File | `fopen()`              |
| Read from File     | `fscanf()`, `fgets()`  |
| Write to File      | `fprintf()`, `fputs()` |
| Close File         | `fclose()`             |

---

# Opening or Creating a File

### Syntax

```c
FILE *fp;
fp = fopen("data.txt", "w");
```

---

# File Modes

| Mode | Description                                          |
| ---- | ---------------------------------------------------- |
| r    | Read file                                            |
| w    | Write file (creates new or overwrites existing file) |
| a    | Append data to existing file                         |
| r+   | Read and write                                       |
| w+   | Read and write (overwrite file)                      |
| a+   | Read and append                                      |

---

# Creating a File

```c
#include <stdio.h>

int main() {

    FILE *fp;

    fp = fopen("data.txt", "w");

    fclose(fp);

    return 0;
}
```

If the file does not exist, it will be **created automatically**.

---

# Writing to a File

```c
#include <stdio.h>

int main() {

    FILE *fp;

    fp = fopen("data.txt", "w");

    fprintf(fp, "Hello File\n");
    fprintf(fp, "Welcome to C programming");

    fclose(fp);

    return 0;
}
```

`fprintf()` works similar to `printf()` but writes data **into a file**.

---

# Appending Data to a File

Append mode adds data **without deleting existing content**.

```c
fp = fopen("data.txt", "a");
fprintf(fp, "\nWelcome again!");
fclose(fp);
```

---

# Reading from a File (Single Line)

```c
#include <stdio.h>

int main() {

    FILE *fp;
    char text[100];

    fp = fopen("data.txt", "r");

    fgets(text, 100, fp);

    printf("%s", text);

    fclose(fp);

    return 0;
}
```

`fgets()` reads **one line at a time**.

---

# Reading All Lines from a File

To read the entire file we use a loop.

```c
char text[100];

fp = fopen("data.txt", "r");

while (fgets(text, 100, fp) != NULL) {
    printf("%s", text);
}

fclose(fp);
```

Explanation:

* `fgets()` reads one line
* When **End Of File (EOF)** is reached, it returns `NULL`
* The loop stops automatically

---

# Another Way to Read Using a Variable

```c
char text[100];
char *data;

fp = fopen("data.txt", "r");

data = fgets(text, 100, fp);

while (data != NULL) {
    printf("%s", text);
    data = fgets(text, 100, fp);
}

fclose(fp);
```

Here:

* `fgets()` returns a **pointer to the string**
* When file ends, it returns **NULL**

---

# Checking if File Opened Successfully

Always check if the file opened correctly.

```c
fp = fopen("data.txt", "r");

if (fp == NULL) {
    printf("File cannot be opened");
    return 1;
}
```

This prevents program crashes.

---

# Closing a File

```c
fclose(fp);
```

Closing the file ensures:

* Data is saved
* Memory resources are released
* File is unlocked

---

# Important Functions Summary

| Function    | Purpose               |
| ----------- | --------------------- |
| `fopen()`   | Opens a file          |
| `fprintf()` | Writes formatted data |
| `fgets()`   | Reads a line          |
| `fscanf()`  | Reads formatted input |
| `fclose()`  | Closes a file         |

---

# 15_Preprocessor_Directives.md

# Preprocessor Directives in C

Preprocessor directives are **instructions processed before compilation**.

They start with the `#` symbol.

Example:

```c
#include <stdio.h>
```

---

# Common Directives

| Directive  | Purpose                        |
| ---------- | ------------------------------ |
| `#include` | Includes header files          |
| `#define`  | Defines constants/macros       |
| `#undef`   | Removes a macro                |
| `#ifdef`   | Checks if macro is defined     |
| `#ifndef`  | Checks if macro is not defined |

---

# #include

Used to include header files.

```c
#include <stdio.h>
```

Types:

```
#include <stdio.h>   → system header
#include "file.h"    → user defined header
```

---

# #define

Defines constants or macros.

```c
#define PI 3.14
```

Example:

```c
#include <stdio.h>
#define PI 3.14

int main() {

    float r = 5;
    float area;

    area = PI * r * r;

    printf("Area = %f", area);

    return 0;
}
```

---

# Macro Example

```c
#define SQUARE(x) x*x
```

Usage:

```c
int result = SQUARE(5);
```

---

# #undef

Removes a defined macro.

```c
#define PI 3.14
#undef PI
```

---

# #ifdef

Checks if a macro is defined.

```c
#define DEBUG

#ifdef DEBUG
printf("Debug Mode Enabled");
#endif
```

---

# #ifndef

Checks if a macro is **not defined**.

```c
#ifndef PI
#define PI 3.14
#endif
```

Often used in **header file protection**.


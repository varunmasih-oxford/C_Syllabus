# 14_File_Handling.md

## File Handling in C

File handling allows programs to store data permanently in files instead of only in RAM.

### Common File Operations

| Operation          | Function           |
| ------------------ | ------------------ |
| Create / Open File | fopen()            |
| Read from File     | fscanf(), fgets()  |
| Write to File      | fprintf(), fputs() |
| Close File         | fclose()           |

---

## Opening or Creating a File

Syntax

```c
FILE *fp;
fp = fopen("data.txt", "w");
```

### File Modes

| Mode | Description                            |
| ---- | -------------------------------------- |
| r    | Read file                              |
| w    | Write file (creates new or overwrites) |
| a    | Append data                            |
| r+   | Read and write                         |
| w+   | Read and write (overwrite)             |
| a+   | Read and append                        |

---

## Writing to a File

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

---

## Reading from a File

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

---

## Closing a File

```c
fclose(fp);
```

Closing the file ensures data is saved and memory resources are released.

---

# 15_Preprocessor_Directives.md

## Preprocessor Directives in C

Preprocessor directives are instructions processed before compilation. They start with the `#` symbol.

### Common Directives

| Directive | Purpose                        |
| --------- | ------------------------------ |
| #include  | Includes header files          |
| #define   | Defines constants/macros       |
| #undef    | Removes a macro                |
| #ifdef    | Checks if macro is defined     |
| #ifndef   | Checks if macro is not defined |

---

## #include

Used to include header files.

```c
#include <stdio.h>
```

---

## #define

Defines constants or macros.

```c
#define PI 3.14
```

Example

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

## #undef

Removes a defined macro.

```c
#define PI 3.14
#undef PI
```

---

## #ifdef

Checks if a macro is defined.

```c
#define DEBUG

#ifdef DEBUG
printf("Debug Mode Enabled");
#endif
```

---

## #ifndef

Checks if a macro is not defined.

```c
#ifndef PI
#define PI 3.14
#endif
```

## 19: Error Handling

C does not provide built-in exception handling like Java or Python.  
Instead, errors are handled using **return values, errno, perror(), and strerror()**.

---

# 1. What is Error Handling?

Error handling is the process of **detecting and responding to errors in a program** so the program does not crash unexpectedly.

Common errors:

- File not found
- Division by zero
- Memory allocation failure
- Invalid input

Without error handling, programs may produce **wrong results or crash**.

---

# 2. Error Handling Using Return Values

Many C functions return a value to indicate **success or failure**.

Example: Division Program

```c
#include <stdio.h>

int main() {
    int a, b;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    if(b == 0) {
        printf("Error: Division by zero is not allowed\n");
        return 1;
    }

    printf("Result = %d\n", a/b);

    return 0;
}

---
# errno, perror(), and strerror() in C

These are used in C for **system error handling**.  
They help programmers understand **why a function failed**.

---

# 1. errno

## What is errno?

`errno` is a **global integer variable** that stores an **error code** when a system function fails.

When functions like `fopen()`, `malloc()`, `open()`, etc. fail, they set the value of `errno`.

Header file:

```c
#include <errno.h>
````

---

## Example

```c
#include <stdio.h>
#include <errno.h>

int main() {

    FILE *fp;

    fp = fopen("data.txt", "r");

    if(fp == NULL) {
        printf("Error number: %d\n", errno);
    }

    return 0;
}
```

Example Output:

```
Error number: 2
```

Explanation:

* Error code **2** usually means **No such file or directory**.

---

## Important Points

* `errno` only stores the **error number**
* It does **not display the error message**
* The value changes whenever a **system function fails**

---

# 2. perror()

## What is perror()?

`perror()` prints a **human-readable error message** based on the value of `errno`.

Header file:

```c
#include <stdio.h>
```

---

## Example

```c
#include <stdio.h>

int main() {

    FILE *fp;

    fp = fopen("data.txt", "r");

    if(fp == NULL) {
        perror("File Error");
    }

    return 0;
}
```

Example Output:

```
File Error: No such file or directory
```

Explanation:

* `"File Error"` → custom message
* `"No such file or directory"` → system message based on `errno`

---

## Syntax

```
perror("Custom Message");
```

Output format:

```
Custom Message : System Error Message
```

---

# 3. strerror()

## What is strerror()?

`strerror()` converts an **error number (`errno`) into a readable string**.

Header files:

```c
#include <string.h>
#include <errno.h>
```

---

## Example

```c
#include <stdio.h>
#include <errno.h>
#include <string.h>

int main() {

    FILE *fp;

    fp = fopen("data.txt", "r");

    if(fp == NULL) {
        printf("Error: %s\n", strerror(errno));
    }

    return 0;
}
```

Example Output:

```
Error: No such file or directory
```

Explanation:

* `errno` contains the error code
* `strerror(errno)` converts it into a readable message

---

# 4. Difference Between errno, perror(), and strerror()

| Feature | errno             | perror()             | strerror()                  |
| ------- | ----------------- | -------------------- | --------------------------- |
| Type    | Variable          | Function             | Function                    |
| Purpose | Stores error code | Prints error message | Converts error code to text |
| Header  | errno.h           | stdio.h              | string.h                    |
| Output  | Error number      | Printed message      | Returns string message      |

---

# 5. Example Using All Three

```c
#include <stdio.h>
#include <errno.h>
#include <string.h>

int main() {

    FILE *fp;

    fp = fopen("data.txt", "r");

    if(fp == NULL) {

        printf("Error number: %d\n", errno);

        perror("Using perror");

        printf("Using strerror: %s\n", strerror(errno));
    }

    return 0;
}
```

Example Output:

```
Error number: 2
Using perror: No such file or directory
Using strerror: No such file or directory
```

---

# Summary

| Tool       | Purpose                                  |
| ---------- | ---------------------------------------- |
| errno      | Stores the error number                  |
| perror()   | Prints the error message automatically   |
| strerror() | Converts error number into readable text |

---

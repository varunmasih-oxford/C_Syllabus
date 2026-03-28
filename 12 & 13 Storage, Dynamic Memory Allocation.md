## 12: Storage Classes

### Types of Storage Classes

| Storage Class | Scope & Lifetime |
| ------------- | ---------------- |
| `auto`        | Local            |
| `static`      | Retains value    |
| `extern`      | Global           |
| `register`    | CPU register     |

---

## 13: Dynamic Memory Allocation

### Memory Functions (`stdlib.h`)

| Function    | Purpose         |
| ----------- | --------------- |
| `malloc()`  | Allocate memory |
| `calloc()`  | Allocate & init |
| `realloc()` | Resize memory   |
| `free()`    | Release memory  |

```c
int *ptr = (int*)malloc(5 * sizeof(int));
```

---

# Stack vs Heap Memory

## 1. Stack Memory

### What is Stack?
Stack is **automatic memory** used for:
- Local variables  
- Function calls  
- Temporary data  

### How it Works
- Memory is allocated **automatically**
- Follows **LIFO (Last In First Out)**

When a function is called → memory is allocated  
When the function ends → memory is automatically removed  

### Example
```c
void fun() {
    int a = 10;  // stored in stack
}
````

* `a` exists only inside the function
* Memory is deleted after function execution

### Key Features

* Fast access
* Limited size
* Managed by compiler
* No need to free memory

---

## 2. Heap Memory

### What is Heap?

Heap is **dynamic memory** used for:

* Runtime allocation
* Large data storage

### How it Works

* Memory is allocated using:

  * `malloc()`
  * `calloc()`
  * `realloc()`

* Memory remains allocated until manually freed

### Example

```c
#include <stdlib.h>

int *ptr = (int*)malloc(5 * sizeof(int));
```

* Memory is allocated in heap
* Pointer `ptr` (stored in stack) points to heap memory

### Key Features

* Slower than stack
* Large memory size
* Managed manually by programmer
* Must use `free()`

---

## Visual Representation

```
STACK                     HEAP
------                    -------
| a  |                    [   ]
| b  | → automatic        [   ] → dynamic
| c  |                    [   ]
------                    -------
```

---

## Comparison Table

| Feature    | Stack          | Heap              |
| ---------- | -------------- | ----------------- |
| Allocation | Automatic      | Manual (`malloc`) |
| Speed      | Fast           | Slower            |
| Size       | Limited        | Large             |
| Lifetime   | Function scope | Until `free()`    |
| Management | Compiler       | Programmer        |
| Access     | Direct         | Via pointer       |

---

## Important Concept

```c
int *ptr = (int*)malloc(sizeof(int));
```

* `ptr` → stored in **stack**
* Allocated memory → stored in **heap**

---

## Common Mistakes

### 1. Memory Leak

```c
malloc(10 * sizeof(int)); // No free()
```

### 2. Invalid Access After Free

```c
free(ptr);
ptr[0] = 10; // Error
```

---

# Dynamic Memory Allocation in C 

---

## Overview

Dynamic Memory Allocation allows you to allocate memory at **runtime** using functions from `<stdlib.h>`.

### Functions Covered

| Function   | Purpose                          |
|------------|----------------------------------|
| malloc()   | Allocate memory (uninitialized)  |
| calloc()   | Allocate + initialize to 0       |
| realloc()  | Resize allocated memory          |
| free()     | Release allocated memory         |

---

## 1. malloc() – Allocate Memory

### Syntax
```c
ptr = (datatype*)malloc(n * sizeof(datatype));
````

### Example

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *ptr;

    ptr = (int*)malloc(3 * sizeof(int));

    if (ptr == NULL) {
        printf("Memory not allocated\n");
        return 1;
    }

    ptr[0] = 10;
    ptr[1] = 20;
    ptr[2] = 30;

    for(int i = 0; i < 3; i++) {
        printf("%d ", ptr[i]);
    }

    free(ptr);
    return 0;
}
```

### Explanation

* Allocates memory for 3 integers
* Memory contains **garbage values initially**
* Values are assigned manually
* Memory is released using `free()`

### Output

```
10 20 30
```

---

## 2. calloc() – Allocate & Initialize

### Syntax

```c
ptr = (datatype*)calloc(n, sizeof(datatype));
```

### Example

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *ptr;

    ptr = (int*)calloc(3, sizeof(int));

    if (ptr == NULL) {
        printf("Memory not allocated\n");
        return 1;
    }

    for(int i = 0; i < 3; i++) {
        printf("%d ", ptr[i]);
    }

    free(ptr);
    return 0;
}
```

### Explanation

* Allocates memory for 3 integers
* Automatically initializes all values to **0**
* No need for manual initialization

### Output

```
0 0 0
```

---

## 3. realloc() – Resize Memory

### Syntax

```c
ptr = (datatype*)realloc(ptr, new_size);
```

### Example

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *ptr;

    ptr = (int*)malloc(2 * sizeof(int));

    ptr[0] = 1;
    ptr[1] = 2;

    ptr = (int*)realloc(ptr, 4 * sizeof(int));

    ptr[2] = 3;
    ptr[3] = 4;

    for(int i = 0; i < 4; i++) {
        printf("%d ", ptr[i]);
    }

    free(ptr);
    return 0;
}
```

### Explanation

* Initial memory for 2 integers
* Resized to 4 integers using `realloc()`
* Old data is preserved
* New memory is added

### Output

```
1 2 3 4
```

---

## 4. free() – Release Memory

### Syntax

```c
free(ptr);
```

### Example

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *ptr;

    ptr = (int*)malloc(2 * sizeof(int));

    ptr[0] = 5;
    ptr[1] = 10;

    printf("%d %d\n", ptr[0], ptr[1]);

    free(ptr);
    ptr = NULL;

    return 0;
}
```

### Explanation

* Releases allocated memory
* Prevents memory leaks
* Setting pointer to NULL avoids dangling pointer

### Output

```
5 10
```

---

## Common Mistakes

### 1. Not freeing memory

```c
malloc(10 * sizeof(int)); // Memory leak
```

### 2. Using pointer after free

```c
free(ptr);
ptr[0] = 10; // Error
```

---

## Best Practices

* Always check for NULL

```c
if(ptr == NULL) {
    printf("Allocation failed");
}
```

* Always free memory

```c
free(ptr);
```

* Set pointer to NULL after freeing

```c
ptr = NULL;
```

---







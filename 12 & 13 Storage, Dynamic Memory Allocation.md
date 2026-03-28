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


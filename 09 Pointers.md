# 9. Pointers

## 1. What is a Pointer?

A **pointer** is a variable that stores the **memory address** of another variable.

Instead of storing a value directly, it stores the location where the value is stored.

### Example

```c
int x = 10;
int *p = &x;
```

### Explanation

- `x` stores the value `10`
- `&x` gives the address of `x`
- `p` stores that address
- `*p` gives the value stored at that address

---

## 2. Understanding Memory Concept

Suppose we have:

```c
int x = 10;
```

Memory representation (example):

| Variable | Value | Address |
|----------|------:|--------:|
| x | 10 | 1000 |

Now:

```c
int *p = &x;
```

| Variable | Value Stored |
|----------|-------------:|
| p | 1000 |

So,

- `p` → `1000` (address of `x`)
- `*p` → `10` (value at that address)

---

## 3. Declaring a Pointer

### Syntax

```c
data_type *pointer_name;
```

### Example

```c
int *p;
float *f;
char *c;
```

> **Important:** The pointer type must match the variable type.

---

## 4. Initializing a Pointer

```c
int x = 10;
int *p = &x;
```

- `&` → Address-of operator
- `*` → Dereference operator

---

## 5. Accessing Pointer Values

```c
#include <stdio.h>

int main() {
    int x = 10;
    int *p = &x;

    printf("%d\n", *p);  // Value of x
    printf("%p\n", p);   // Address of x

    return 0;
}
```

### Output

```
10
1000    // Example address
```

---

## 6. Dereferencing a Pointer

Dereferencing means accessing or modifying the value stored at the memory address pointed to by a pointer.

```c
int x = 10;
int *p = &x;

printf("%d", *p);   // 10
```

If we change the value using the pointer:

```c
*p = 50;
printf("%d", x);    // 50
```

Since `p` points to `x`, modifying `*p` changes the value of `x`.

### Example Program

```c
#include <stdio.h>

int main() {

    // Without Pointer
    // int a = 10;
    // int p = a;
    //
    // p = 100;
    // printf("%d\n", p);
    // printf("%d\n", a);
    //
    // Here, p is just another integer variable.
    // Changing p does NOT affect a.

    // Using Pointer
    int a = 10;
    int *p = &a;

    *p = 100;

    printf("%d\n", *p);   // Value through pointer
    printf("%d\n", a);    // Original variable

    return 0;
}
```

### Output

```
100
100
```

### Explanation

Initially:

| Variable | Value |
|----------|------:|
| a | 10 |
| p | Address of a |

After executing:

```c
*p = 100;
```

- `p` stores the address of `a`.
- `*p` refers to the value stored at that address.
- Assigning `100` to `*p` changes the value of `a`.

### Memory Representation

| Variable | Value | Address (Example) |
|----------|------:|------------------:|
| a | 10 → 100 | 1000 |
| p | 1000 | 2000 |

So,

- `p` → Address of `a`
- `*p` → Value of `a`

### Difference Between Copying and Using a Pointer

```c
// Copying a value
int a = 10;
int b = a;

b = 100;

printf("%d\n", a);   // 10
printf("%d\n", b);   // 100
```

```c
// Using a pointer
int a = 10;
int *p = &a;

*p = 100;

printf("%d\n", a);   // 100
printf("%d\n", *p);  // 100
```

> **Key Point:** A normal variable stores a copy of the value, while a pointer stores the memory address of another variable. Changing the value through a pointer changes the original variable.

---

## 7. Pointer and Arrays

The array name itself is a pointer to the first element.

```c
int arr[3] = {10, 20, 30};
int *p = arr;

printf("%d\n", *p);      // 10
printf("%d\n", *(p+1));  // 20
printf("%d\n", *(p+2));  // 30
```

### Explanation

- `arr` = Address of `arr[0]`
- `p + 1` moves to the next integer
- `*(p + 1)` accesses the second element

---

## 8. Why Use Pointers?

### 1. Dynamic Memory Allocation

Used with:

- `malloc()`
- `calloc()`
- `realloc()`
- `free()`

Example:

```c
#include <stdlib.h>

int *p;
p = (int *)malloc(5 * sizeof(int));
```

This allocates memory during runtime.

---

### 2. Function Call by Reference

Without Pointer

```c
void change(int x) {
    x = 50;
}
```

The original value does **not** change.

With Pointer

```c
void change(int *x) {
    *x = 50;
}

int main() {
    int a = 10;
    change(&a);

    printf("%d", a);
}
```

Output

```
50
```

---

### 3. Efficient Array Handling

Instead of copying large arrays, we pass a pointer.

```c
void printArray(int *arr, int size) {
    for(int i = 0; i < size; i++)
        printf("%d ", arr[i]);
}
```

This is efficient and saves memory.

---

## 9. Pointer to Pointer

```c
int x = 10;
int *p = &x;
int **pp = &p;

printf("%d", **pp);
```

Output

```
10
```

### Explanation

- `p` → Address of `x`
- `pp` → Address of `p`
- `**pp` → Value of `x`

---

## 10. NULL Pointer

A pointer that points to nothing.

```c
int *p = NULL;
```

Always initialize a pointer to `NULL` if it is not assigned to any valid address.

---

## 11. Common Pointer Mistakes

### 1. Uninitialized Pointer

Wrong

```c
int *p;
*p = 10;
```

Correct

```c
int x = 10;
int *p = &x;
```

---

### 2. Dangling Pointer

A pointer that still points to memory after it has been freed.

---

### 3. Memory Leak

Allocating memory with `malloc()` but never freeing it using `free()`.

---

## 12. Pointer Arithmetic

```c
int arr[3] = {10, 20, 30};
int *p = arr;

printf("%d\n", *p);

p++;

printf("%d\n", *p);
```

Output

```
10
20
```

The pointer moves according to the size of its data type.

---

## 13. Practice Programs

1. Swap two numbers using pointers
2. Reverse an array using pointers
3. Dynamic memory allocation for `n` numbers
4. Sum of an array using pointer arithmetic
5. Create your own `strlen()` using pointers

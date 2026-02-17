# 9. Pointers

---

# 1. What is a Pointer?

A **pointer** is a variable that stores the **memory address** of another variable.

Instead of storing a value directly, it stores the **location** where the value is stored.

Example:

```c
int x = 10;
int *p = &x;
````

Explanation:

* `x` stores value 10
* `&x` gives the address of x
* `p` stores that address
* `*p` gives the value at that address

---

# 2. Understanding Memory Concept

Suppose:

```c
int x = 10;
```

Memory representation (example address):

| Variable | Value | Address |
| -------- | ----- | ------- |
| x        | 10    | 1000    |

Now:

```c
int *p = &x;
```

| Variable | Value Stored |
| -------- | ------------ |
| p        | 1000         |

So:

* `p` → 1000 (address of x)
* `*p` → 10 (value at that address)

---

# 3. Declaring a Pointer

### Syntax:

```c
data_type *pointer_name;
```

Example:

```c
int *p;
float *f;
char *c;
```

Important:
Pointer type must match variable type.

---

# 4. Initializing a Pointer

```c
int x = 10;
int *p = &x;
```

* `&` → Address-of operator
* `*` → Dereference operator

---

# 5. Accessing Pointer Values

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

Output:

```
10
1000  (example address)
```

---

# 6. Dereferencing a Pointer

Dereferencing means accessing the value stored at the address.

```c
int x = 10;
int *p = &x;

printf("%d", *p);  // 10
```

If we change value using pointer:

```c
*p = 50;
printf("%d", x);  // 50
```

The original variable changes!

---

# 7. Pointer and Arrays

Array name itself is a pointer to first element.

```c
int arr[3] = {10, 20, 30};
int *p = arr;

printf("%d\n", *p);      // 10
printf("%d\n", *(p+1));  // 20
printf("%d\n", *(p+2));  // 30
```

Explanation:

* `arr` = address of arr[0]
* `p+1` moves to next integer location

---

# 8. Why Use Pointers?

## 1. Dynamic Memory Allocation

Used with:

* malloc()
* calloc()
* realloc()
* free()

Example:

```c
#include <stdlib.h>

int *p;
p = (int*) malloc(5 * sizeof(int));
```

This creates memory during runtime.

---

## 2. Function Call by Reference

Without pointer:

```c
void change(int x) {
    x = 50;
}
```

Original value does NOT change.

With pointer:

```c
void change(int *x) {
    *x = 50;
}

int main() {
    int a = 10;
    change(&a);
    printf("%d", a);  // 50
}
```

Now original value changes.

---

## 3. Efficient Array Handling

Instead of copying large arrays, we pass pointer.

```c
void printArray(int *arr, int size) {
    for(int i = 0; i < size; i++)
        printf("%d ", arr[i]);
}
```

Efficient and memory-saving.

---

# 9. Pointer to Pointer

```c
int x = 10;
int *p = &x;
int **pp = &p;

printf("%d", **pp);  // 10
```

Explanation:

* p → address of x
* pp → address of p
* **pp → value of x

---

# 10. NULL Pointer

A pointer that points to nothing.

```c
int *p = NULL;
```

Always initialize pointer to NULL if not assigned.

---

# 11. Common Pointer Mistakes

1. Uninitialized pointer

Wrong:

```c
int *p;
*p = 10;   // Dangerous
```

Correct:

```c
int x = 10;
int *p = &x;
```

2. Dangling pointer (memory freed but still used)

3. Memory leak (malloc but no free)

---

# 12. Pointer Arithmetic

```c
int arr[3] = {10, 20, 30};
int *p = arr;

printf("%d\n", *p);     // 10
p++;
printf("%d\n", *p);     // 20
```

Pointer moves according to data type size.

---

# 13. Practice Programs

1. Swap two numbers using pointers
2. Reverse array using pointers
3. Dynamic memory allocation for n numbers
4. Sum of array using pointer arithmetic
5. Create your own strlen using pointer

---

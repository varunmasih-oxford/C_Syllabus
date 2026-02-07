## 7: Arrays

# 7. Arrays in C (Step-by-Step Tutorial)

## 1. What is an Array?

An **array** is a collection of elements of the **same data type** stored in **contiguous memory locations**.

Each element is accessed using an **index number** starting from **0**.

Example visualization:

| Index | 0 | 1 | 2 | 3 | 4 |
|------|----|----|----|----|----|
| Value | 10 | 20 | 30 | 40 | 50 |

---

## 2. Why Do We Need Arrays?

Without arrays:
```c
int a = 10, b = 20, c = 30, d = 40, e = 50;
````

With arrays:

```c
int arr[5] = {10, 20, 30, 40, 50};
```

Arrays make code **shorter, cleaner, and easier to manage**.

---

## 3. Declaring an Array

### Syntax:

```c
data_type array_name[size];
```

### Example:

```c
int arr[5];
```

This creates space for **5 integers** in memory.

---

## 4. Initializing an Array

### Method 1: During Declaration

```c
int arr[5] = {10, 20, 30, 40, 50};
```

### Method 2: Without Size (Compiler counts)

```c
int arr[] = {10, 20, 30, 40, 50};
```

### Method 3: Assigning Values Later

```c
int arr[5];
arr[0] = 10;
arr[1] = 20;
```

---

## 5. Accessing Array Elements

Array index starts from **0**.

```c
#include <stdio.h>

int main() {
    int arr[5] = {10, 20, 30, 40, 50};

    printf("%d\n", arr[0]); // 10
    printf("%d\n", arr[2]); // 30
    printf("%d\n", arr[4]); // 50

    return 0;
}
```

---

## 6. Modifying Array Values

```c
arr[1] = 99;
printf("%d", arr[1]);  // 99
```

---

## 7. Looping Through an Array

```c
#include <stdio.h>

int main() {
    int arr[5] = {10, 20, 30, 40, 50};

    for(int i = 0; i < 5; i++) {
        printf("%d ", arr[i]);
    }

    return 0;
}
```

**Output:**

```
10 20 30 40 50
```

---

# One-Dimensional Array (1D)

A **1D array** is like a single list of elements.

```c
int arr[5] = {10, 20, 30, 40, 50};
```

---

# Two-Dimensional Array (2D Array)

A **2D array** is like a **table with rows and columns**.

---

## 8. Declaring a 2D Array

### Syntax:

```c
data_type array_name[rows][columns];
```

### Example:

```c
int matrix[2][2];
```

This means:

* 2 rows
* 2 columns
* Total elements = 4

---

## 9. Initializing a 2D Array

```c
int matrix[2][2] = {
    {1, 2},
    {3, 4}
};
```

Table form:

|       | Col 0 | Col 1 |
| ----- | ----- | ----- |
| Row 0 | 1     | 2     |
| Row 1 | 3     | 4     |

---

## 10. Accessing 2D Array Elements

### Syntax:

```c
array[row][column]
```

```c
printf("%d", matrix[0][0]); // 1
printf("%d", matrix[1][1]); // 4
```

---

## 11. Looping Through a 2D Array

```c
#include <stdio.h>

int main() {
    int matrix[2][2] = {{1, 2}, {3, 4}};

    for(int i = 0; i < 2; i++) {
        for(int j = 0; j < 2; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```

**Output:**

```
1 2
3 4
```

---

## 12. Memory Concept

### 1D Array (Contiguous Memory)

```
arr[0] → arr[1] → arr[2] → arr[3] → arr[4]
```

### 2D Array (Row-Major Order in C)

```
matrix[0][0], matrix[0][1], matrix[1][0], matrix[1][1]
```

C stores 2D arrays **row by row**.

---

## 13. Common Mistakes

❌ Out-of-bounds access:

```c
arr[5] = 100;  // Wrong (valid index: 0–4)
```

❌ Wrong loop condition:

```c
for(int i = 0; i <= 5; i++)  // Wrong
```

✅ Correct loop:

```c
for(int i = 0; i < 5; i++)
```

---

## 14. Practice Ideas

Try writing programs to:

* Take array input from user
* Find sum and average
* Find largest and smallest element
* Add two 2D matrices


---

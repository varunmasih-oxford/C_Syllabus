## 8: Strings

### What is a String?

* A string is an **array of characters**
* Ends with **null character `\\0`**

```c
char name[] = "C Programming";
```

---

### String Input/Output

```c
char name[20];
scanf("%s", name);
printf("%s", name);
```

---

### Common String Functions (`string.h`)

| Function   | Purpose     |
| ---------- | ----------- |
| `strlen()` | Length      |
| `strcpy()` | Copy        |
| `strcmp()` | Compare     |
| `strcat()` | Concatenate |

---



# 8. Strings in C (Detailed Step-by-Step Guide)

---

# 1. What is a String?

A **string** in C is an **array of characters** that ends with a special character called the **null character**.

The null character is:

\0   (backslash zero)

It tells the compiler where the string ends.

Example:

```c
char name[] = "C Programming";
````

This is stored in memory as:

| C |   | P | r | o | g | r | a | m | m | i | n | g | \0 |

Important:

* Even if the string has 13 characters, memory will store 14 (including `\0`).

---

# 2. Declaring Strings

### Method 1: Using Array and String Literal

```c
char name[] = "Hello";
```

### Method 2: Using Character Array

```c
char name[6] = {'H', 'e', 'l', 'l', 'o', '\0'};
```

### Method 3: Declaring Empty String

```c
char name[20];
```

---

# 3. How Strings Are Stored in Memory

Example:

```c
char name[] = "Hello";
```

Memory layout:

| Index | Value |
| ----- | ----- |
| 0     | H     |
| 1     | e     |
| 2     | l     |
| 3     | l     |
| 4     | o     |
| 5     | \0    |

C always adds `\0` automatically when using double quotes.

---

# 4. String Input and Output

## 4.1 Using scanf()

```c
#include <stdio.h>

int main() {
    char name[20];

    scanf("%s", name);
    printf("%s", name);

    return 0;
}
```

Important:

* `scanf("%s", name);` stops reading at space.
* It cannot take full name like "Varun Masih".

Example:
Input:

```
Varun Masih
```

Output:

```
Varun
```

---

## 4.2 Using gets() (Not Recommended)

```c
gets(name);
```

Problem:

* Unsafe
* Removed in newer C versions

---

## 4.3 Using fgets() (Recommended)

```c
#include <stdio.h>

int main() {
    char name[50];

    fgets(name, sizeof(name), stdin);
    printf("%s", name);

    return 0;
}
```

* Can read spaces
* Safe method

---

# 5. String Output

```c
printf("%s", name);
puts(name);
```

Difference:

* `puts()` automatically adds new line
* `printf()` does not

---

# 6. Common String Functions (string.h)

To use string functions, include:

```c
#include <string.h>
```

---

## 6.1 strlen() – Find Length

Returns length of string (excluding `\0`).

```c
#include <stdio.h>
#include <string.h>

int main() {
    char name[] = "Hello";
    printf("%lu", strlen(name));
    return 0;
}
```

Output:

```
5
```

---

## 6.2 strcpy() – Copy String

Copies one string into another.

```c
char source[] = "Hello";
char dest[20];

strcpy(dest, source);
printf("%s", dest);
```

Output:

```
Hello
```

---

## 6.3 strcmp() – Compare Strings

Compares two strings.

```c
char a[] = "Apple";
char b[] = "Apple";

if(strcmp(a, b) == 0)
    printf("Equal");
else
    printf("Not Equal");
```

Return Values:

* 0 → Equal
* <0 → First string smaller
* > 0 → First string greater

---

## 6.4 strcat() – Concatenate Strings

Joins two strings.

```c
char a[20] = "Hello ";
char b[] = "World";

strcat(a, b);
printf("%s", a);
```

Output:

```
Hello World
```

Important:

* Destination must have enough space.

---

# 7. Manual String Traversal Using Loop

```c
#include <stdio.h>

int main() {
    char name[] = "Hello";

    for(int i = 0; name[i] != '\0'; i++) {
        printf("%c\n", name[i]);
    }

    return 0;
}
```

---

# 8. Common Mistakes

1. Forgetting space for null character

Wrong:

```c
char name[5] = "Hello";
```

Correct:

```c
char name[6] = "Hello";
```

2. Using == to compare strings

Wrong:

```c
if(a == b)
```

Correct:

```c
if(strcmp(a, b) == 0)
```

3. Buffer overflow (small array size)

Always ensure array size is large enough.

---

# 9. Practice Programs

1. Find length of string without using strlen()
2. Reverse a string
3. Check palindrome
4. Count vowels and consonants
5. Convert string to uppercase
6. Concatenate without using strcat()

---





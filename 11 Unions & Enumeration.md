## 11: Unions & Enumerations

### Union

* Similar to structure
* **Shares memory**

```c
union Data {
    int i;
    float f;
};
```
```
#include <stdio.h>

union SharedMemory {
    char a;    // 1 byte
    int b;     // 4 bytes
    double c;  // 8 bytes
};

int main() {
    union SharedMemory u;

    // Print the memory addresses of the union itself and its members
    printf("Address of union 'u': %p\n", (void*)&u);
    printf("Address of member a:  %p\n", (void*)&u.a);
    printf("Address of member b:  %p\n", (void*)&u.b);
    printf("Address of member c:  %p\n", (void*)&u.c);

    return 0;
}
```


---
# Enumeration (`enum`) in C

An **enumeration (`enum`)** is a user-defined data type that assigns meaningful names to integer constants, making programs easier to read and understand.

## Example: Days of the Week

```c
#include <stdio.h>

// Enumeration (enum)
enum Day
{
    Mon,
    Tue,
    Wed
};

int main()
{
    enum Day today = Tue;

    if (today == Tue)
    {
        printf("Today is Tuesday\n");
    }

    printf("Numeric value of Tue = %d\n", today);

    return 0;
}
```

### Output

```text
Today is Tuesday
Numeric value of Tue = 1
```

### Explanation

- `enum Day` defines a new data type named `Day`.
- `Mon`, `Tue`, and `Wed` are enumeration constants.
- By default:
  - `Mon = 0`
  - `Tue = 1`
  - `Wed = 2`
- The variable `today` is declared as `enum Day` and stores one of the enumeration values.
- Enumerations improve code readability by using meaningful names instead of integer values.

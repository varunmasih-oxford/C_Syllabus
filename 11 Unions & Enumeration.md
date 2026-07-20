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

### Enumeration (`enum`)
An **enumeration (`enum`)** is a user-defined data type that assigns names to a set of integer constants, making the code more readable.


## Example: Days of the Week

```cpp
#include <iostream>
using namespace std;

// Enumeration (enum)
enum Day
{
    Mon,
    Tue,
    Wed
};

int main()
{
    Day today = Tue;

    if (today == Tue)
    {
        cout << "Today is Tuesday" << endl;
    }

    cout << "Numeric value of Tue = " << today << endl;

    return 0;
}
```

### Output

```text
Today is Tuesday
Numeric value of Tue = 1
```

### Explanation

- `enum Day` creates a new data type named `Day`.
- `Mon`, `Tue`, and `Wed` are named constants.
- By default:
  - `Mon = 0`
  - `Tue = 1`
  - `Wed = 2`
- The variable `today` stores one of the enumeration values, making the program more readable than using integer values directly.

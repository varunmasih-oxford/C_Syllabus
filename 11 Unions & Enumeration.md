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

```c
enum Day {Mon, Tue, Wed};
```

---

## 6: Functions

### What is a Function?

* A **block of code** that performs a specific task
* Helps in **code reuse** and **modularity**

### Types of Functions

* Library functions → `printf()`, `scanf()`
* User-defined functions

---

### Function Syntax

```c
return_type function_name(parameters) {
    // code
}
```

### Example

```c
int add(int a, int b) {
    return a + b;
}

int main() {
    printf("%d", add(5, 3));
    return 0;
}
```


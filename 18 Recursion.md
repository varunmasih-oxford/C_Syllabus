## 18: Recursion

### What is Recursion?

* A function calling itself

```c
int factorial(int n) {
    if(n == 0)
        return 1;
    return n * factorial(n-1);
}
```


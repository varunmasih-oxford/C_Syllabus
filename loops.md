## 5: Looping Statements

### Why Loops?

* Used to **repeat code**
* Saves time and reduces errors

---

### `for` Loop

```c
for(int i = 1; i <= 5; i++) {
    printf("%d ", i);
}
```

---

### `while` Loop

```c
int i = 1;
while(i <= 5) {
    printf("%d ", i);
    i++;
}
```

---

### `do-while` Loop

* Executes **at least once**

```c
int i = 1;
do {
    printf("%d ", i);
    i++;
} while(i <= 5);
```

---

### Loop Control Statements

* `break` → Exit loop
* `continue` → Skip iteration

---


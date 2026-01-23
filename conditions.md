## 4: Decision Making Statements

### Why Decision Making?

* Allows a program to **choose different paths**
* Based on conditions

---

### `if` Statement

```c
if(condition) {
    // code
}
```

```c
if(age >= 18)
    printf("Adult");
```

---

### `if-else` Statement

```c
if(age >= 18)
    printf("Eligible to vote");
else
    printf("Not eligible");
```

---

### `else-if` Ladder

```c
if(marks >= 90)
    printf("Grade A");
else if(marks >= 75)
    printf("Grade B");
else
    printf("Grade C");
```

---

### `switch` Statement

* Used when multiple fixed choices exist

```c
switch(choice) {
    case 1:
        printf("Addition");
        break;
    case 2:
        printf("Subtraction");
        break;
    default:
        printf("Invalid choice");
}
```

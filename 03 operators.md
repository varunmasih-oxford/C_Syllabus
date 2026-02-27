## 3: Operators & Expressions

### What is an Operator?

* An **operator** is a symbol that performs an operation on variables or values
* The values on which operators work are called **operands**

### Types of Operators in C

#### Arithmetic Operators

| Operator | Meaning        | Example |
| -------- | -------------- | ------- |
| `+`      | Addition       | `a + b` |
| `-`      | Subtraction    | `a - b` |
| `*`      | Multiplication | `a * b` |
| `/`      | Division       | `a / b` |
| `%`      | Modulus        | `a % b` |

```c
int a = 10, b = 3;
printf("%d", a % b);   // Output: 1
```

#### Relational Operators

* Used to compare values
* Result is **true (1)** or **false (0)**

| Operator | Meaning          |
| -------- | ---------------- |
| `>`      | Greater than     |
| `<`      | Less than        |
| `>=`     | Greater or equal |
| `<=`     | Less or equal    |
| `==`     | Equal to         |
| `!=`     | Not equal to     |

#### Logical Operators

| Operator | Meaning |   |    |
| -------- | ------- | - | -- |
| `&&`     | AND     |   |    |
| `        |         | ` | OR |
| `!`      | NOT     |   |    |

```c
if(age > 18 && age < 60)
    printf("Working age");
```

#### Assignment Operators

* Assign values to variables

```c
int x = 10;
x += 5;   // x = x + 5
```

---


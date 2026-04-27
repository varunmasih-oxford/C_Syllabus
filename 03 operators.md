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

# Practical Questions: Operators & Expressions in C

## 1. Arithmetic Operations
Write a program to input two integers and perform:
- Addition
- Subtraction
- Multiplication
- Division
- Modulus

---

## 2. Compare Two Numbers
Write a program to check whether one number is:
- Greater than
- Less than
- Equal to another number

---

## 3. Even or Odd
Write a program to check whether a number is even or odd using the modulus (%) operator.

---

## 4. Largest of Two Numbers
Write a program to find the largest of two numbers using relational operators.

---

## 5. Voting Eligibility
Write a program to check if a person is eligible to vote (age ≥ 18).

---

## 6. Number in Range
Write a program to check if a number lies between 10 and 50 using logical AND (&&).

---

## 7. Divisibility Check
Write a program to check if a number is divisible by 3 OR 5 using logical OR (||).

---

## 8. NOT Operator Usage
Write a program to check if a number is not equal to zero using NOT (!) operator.

---

## 9. Assignment Operators
Write a program to:
- Initialize a variable
- Update it using +=, -=, *= operators
- Display the result after each operation

---

## 10. Total and Average
Write a program to input three numbers and calculate:
- Total
- Average


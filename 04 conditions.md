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
# Practical Questions: Decision Making Statements in C

## 1. Positive or Negative
Write a program to check whether a number is positive or negative using `if`.

---

## 2. Voting Eligibility
Write a program to check if a person is eligible to vote using `if-else`.

---

## 3. Largest of Two Numbers
Write a program to find the largest of two numbers using `if-else`.

---

## 4. Even or Odd
Write a program to check whether a number is even or odd using `if-else`.

---

## 5. Grade Calculation
Write a program to assign grades based on marks using `else-if ladder`.

---

## 6. Leap Year
Write a program to check whether a year is a leap year or not.

---

## 7. Largest of Three Numbers
Write a program to find the largest of three numbers using `else-if`.

---

## 8. Vowel or Consonant
Write a program to check if a character is a vowel or consonant.

---

## 9. Calculator using Switch
Write a menu-driven program using `switch` to perform:
- Addition
- Subtraction

---

## 10. Day of the Week
Write a program using `switch` to display the day of the week based on a number (1–7).

---

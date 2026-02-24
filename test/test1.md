# C Programming Practical Test

## Simple Banking System


Total Marks: 50

---

## Problem Statement

Write a C program to create a Simple Bank Account System.

The program should:

1. Accept customer details.
2. Allow deposit and withdrawal.
3. Show current balance.
4. Use a menu-driven system.

---

## Requirements

### Part 1 – Customer Details (Strings) – 10 Marks

* Accept:

  * Customer Name
  * Account Number
* Display welcome message:

```
Welcome, <Customer Name>
```

---

### Part 2 – Initial Balance (Variables & Operators) – 5 Marks

* Accept initial balance from the user.

---

### Part 3 – Menu Driven Operations (Loop + Conditions) – 20 Marks

Create a menu using a `do-while` loop:

```
1. Deposit
2. Withdraw
3. Check Balance
4. Show Last 3 Transactions
5. Exit
```

* Deposit

  * Accept amount
  * Add to balance

* Withdraw

  * Accept amount
  * Check if balance is sufficient
  * If not, display "Insufficient Balance"

* Check Balance

  * Display current balance

* The loop continues until the user selects Exit.

---

### Part 4 – Use of Functions – 10 Marks

Create at least 3 functions:

```c
void deposit(float *balance);
void withdraw(float *balance);
void checkBalance(float balance);
```

---

### Part 5 – Use Array – 5 Marks

* Store the last 3 transactions in an array.
* Display them when the user selects “Show Last 3 Transactions”.

---

## Concepts Covered

* Strings – Customer name
* Arrays – Store transactions
* Loops – Menu repetition
* Conditions – Withdrawal check
* Functions – Deposit and withdraw operations
* Operators – Arithmetic and relational operators

## 10: Structures


## Step 1: Problem Without Structure

Suppose you want to store a student's details:

- Roll Number
- Name
- Marks

Without structure:

```c
int roll = 1;
char name[20] = "Rahul";
float marks = 85.5;
````

Problem:

* Data is separate
* Hard to manage multiple students
* No logical grouping

---

## Step 2: What is a Structure?

A Structure is a **user-defined data type** that groups different types of data into a single unit.

Example:

```
Student = roll + name + marks
```

---

## Step 3: Structure Syntax

```c
struct Student {
    int roll;
    char name[20];
    float marks;
};
```

### Explanation

| Part              | Meaning           |
| ----------------- | ----------------- |
| struct            | keyword           |
| Student           | structure name    |
| roll, name, marks | structure members |

This only defines the structure.
No memory is allocated yet.

---

## Step 4: Creating Structure Variable

```c
struct Student s1;
```

Now memory is allocated.

`s1` represents one student.

---

## Step 5: Access Structure Members

Use dot (.) operator.

```c
s1.roll = 1;
```

### Example

```c
#include <stdio.h>

struct Student {
    int roll;
    char name[20];
    float marks;
};

int main() {

    struct Student s1;

    s1.roll = 1;
    s1.marks = 90.5;

    printf("Roll: %d\n", s1.roll);
    printf("Marks: %.2f\n", s1.marks);

    return 0;
}
```

---

## Step 6: Taking Input in Structure

```c
#include <stdio.h>

struct Student {
    int roll;
    char name[20];
    float marks;
};

int main() {

    struct Student s1;

    printf("Enter Roll: ");
    scanf("%d", &s1.roll);

    printf("Enter Name: ");
    scanf("%s", s1.name);

    printf("Enter Marks: ");
    scanf("%f", &s1.marks);

    printf("\nStudent Details\n");
    printf("%d %s %.2f",
           s1.roll,
           s1.name,
           s1.marks);

    return 0;
}
```

---

## Step 7: Structure Initialization

```c
struct Student s1 = {1, "Amit", 88.5};
```

Values must follow member order.

---

## Step 8: Array of Structures

Used for multiple records.

```c
struct Student s[3];
```

Example:

```c
for(int i=0;i<3;i++){
    scanf("%d %s %f",
          &s[i].roll,
          s[i].name,
          &s[i].marks);
}
```

Acts like a mini database.

---

## Step 9: Structure Inside Function

### Passing Structure to Function

```c
void display(struct Student s) {
    printf("%d %s %.2f", s.roll, s.name, s.marks);
}
```

Call:

```c
display(s1);
```

---

## Step 10: Pointer to Structure

Create pointer:

```c
struct Student *ptr = &s1;
```

Access using arrow operator:

```c
ptr->roll;
```

Equivalent:

```c
(*ptr).roll;
```

---

## Step 11: Typedef with Structure (Professional Method)

```c
typedef struct {
    int roll;
    char name[20];
    float marks;
} Student;
```

Now create variable:

```c
Student s1;
```

---

## Step 12: Real-World Example

```c
#include <stdio.h>

typedef struct {
    int id;
    char name[20];
    float salary;
} Employee;

int main() {

    Employee e1 = {101, "Ravi", 45000};

    printf("%d %s %.2f",
           e1.id,
           e1.name,
           e1.salary);

    return 0;
}
```

---

## Step 13: When to Use Structures

Use structures when building:

* Student Management System
* Employee Records
* Library System
* Banking Application
* Product Inventory
* Database-like programs

---

## Step 14: Important Operators

| Operator | Use                   |
| -------- | --------------------- |
| .        | Access member         |
| ->       | Pointer member access |
| &        | Address of structure  |
| typedef  | Create alias name     |

---

## Step 15: Memory Concept

Structure memory equals sum of all members.

Example:

```c
struct Test {
    int a;
    float b;
    char c;
};
```

Approximate memory:

```
4 + 4 + 1 = 9 bytes
```

(Compiler may add padding.)


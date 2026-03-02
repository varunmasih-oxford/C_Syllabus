1. Structure: Book (Define and Print)

```c
#include <stdio.h>
#include <string.h>

struct Book {
    int book_id;
    char title[30];
    float price;
};

int main() {
    struct Book b1;

    b1.book_id = 101;
    strcpy(b1.title, "C Programming");
    b1.price = 299.50;

    printf("Book ID: %d\n", b1.book_id);
    printf("Title: %s\n", b1.title);
    printf("Price: %.2f\n", b1.price);

    return 0;
}
```

---

2. Structure Initialization at Declaration

```c
#include <stdio.h>

struct Book {
    int book_id;
    char title[30];
    float price;
};

int main() {

    struct Book b1 = {102, "Data Structures", 450.75};

    printf("Book ID: %d\n", b1.book_id);
    printf("Title: %s\n", b1.title);
    printf("Price: %.2f\n", b1.price);

    return 0;
}
```

---

3. Student Structure (User Input)

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
    printf("%d %s %.2f\n", s1.roll, s1.name, s1.marks);

    return 0;
}
```

---

4. Array of Structures (3 Students)

```c
#include <stdio.h>

struct Student {
    int roll;
    char name[20];
    float marks;
};

int main() {

    struct Student s[3];

    for(int i = 0; i < 3; i++) {
        printf("\nStudent %d\n", i+1);
        printf("Enter Roll: ");
        scanf("%d", &s[i].roll);
        printf("Enter Name: ");
        scanf("%s", s[i].name);
        printf("Enter Marks: ");
        scanf("%f", &s[i].marks);
    }

    printf("\n--- Student Details ---\n");
    for(int i = 0; i < 3; i++) {
        printf("%d %s %.2f\n", s[i].roll, s[i].name, s[i].marks);
    }

    return 0;
}
```

---

5. Employee – Find Highest Salary

```c
#include <stdio.h>

struct Employee {
    int id;
    char name[20];
    float salary;
};

int main() {

    struct Employee e[2];

    for(int i = 0; i < 2; i++) {
        printf("\nEmployee %d\n", i+1);
        printf("Enter ID Name Salary: ");
        scanf("%d %s %f", &e[i].id, e[i].name, &e[i].salary);
    }

    if(e[0].salary > e[1].salary)
        printf("Highest Salary: %s\n", e[0].name);
    else
        printf("Highest Salary: %s\n", e[1].name);

    return 0;
}
```

---

6. Product – Calculate Total Value

```c
#include <stdio.h>

struct Product {
    int product_id;
    char name[20];
    float price;
    int quantity;
};

int main() {

    struct Product p;

    printf("Enter Product ID: ");
    scanf("%d", &p.product_id);

    printf("Enter Name: ");
    scanf("%s", p.name);

    printf("Enter Price: ");
    scanf("%f", &p.price);

    printf("Enter Quantity: ");
    scanf("%d", &p.quantity);

    float total = p.price * p.quantity;

    printf("Total Value: %.2f\n", total);

    return 0;
}
```

---

7. Car – Increase Price by 10%

```c
#include <stdio.h>

struct Car {
    char model[20];
    int year;
    float price;
};

int main() {

    struct Car c = {"HondaCity", 2022, 1000000};

    c.price = c.price + (c.price * 0.10);

    printf("Updated Price: %.2f\n", c.price);

    return 0;
}
```

---

8. Compare Two Students' Marks

```c
#include <stdio.h>

struct Student {
    int roll;
    char name[20];
    float marks;
};

int main() {

    struct Student s1 = {1, "Rahul", 85};
    struct Student s2 = {2, "Aman", 92};

    if(s1.marks > s2.marks)
        printf("%s scored higher\n", s1.name);
    else
        printf("%s scored higher\n", s2.name);

    return 0;
}
```

---

9. Structure with Function

```c
#include <stdio.h>

struct Student {
    int roll;
    char name[20];
    float marks;
};

void display(struct Student s) {
    printf("%d %s %.2f\n", s.roll, s.name, s.marks);
}

int main() {

    struct Student s1 = {1, "Rahul", 88.5};

    display(s1);

    return 0;
}
```

---

10. Nested Structure (Date inside Student)

```c
#include <stdio.h>

struct Date {
    int day;
    int month;
    int year;
};

struct Student {
    int roll;
    char name[20];
    struct Date dob;
};

int main() {

    struct Student s1;

    printf("Enter Roll: ");
    scanf("%d", &s1.roll);

    printf("Enter Name: ");
    scanf("%s", s1.name);

    printf("Enter DOB (dd mm yyyy): ");
    scanf("%d %d %d", &s1.dob.day, &s1.dob.month, &s1.dob.year);

    printf("\nStudent Details\n");
    printf("%d %s %02d/%02d/%d\n",
           s1.roll,
           s1.name,
           s1.dob.day,
           s1.dob.month,
           s1.dob.year);

    return 0;
}

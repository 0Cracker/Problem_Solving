# W3 Material

**🧪 Week 3: Operators and Loops | LabWorks**

*Where Theory Meets Practice 🚀*

---

## 📌 Overview

This week covers the fundamentals of **operators**, **while loops**, and **do-while loops** in C programming. Through hands-on exercises, students will learn how to combine expressions and loop structures to solve problems.

---

## 🟦 Part 1: Basic Arithmetic & Assignment Operators

### 🧠 Concept

- Arithmetic operators: `+`, , , `/`
- Assignment and compound assignment: `=`, `+=`, `=`, `=`, `/=`

### 🧪 Example: Total Purchase Calculator

```c
#include <stdio.h>

int main(void) {
    int total = 0;
    int snacks, drinks;
    int snack_price = 1200;
    int drink_price = 900;

    printf("How many snacks did you buy? ");
    scanf("%d", &snacks);

    printf("How many drinks did you buy? ");
    scanf("%d", &drinks);

    total += snacks * snack_price;
    total += drinks * drink_price;

    printf("Total cost: %d won\n", total);
    return 0;
}
```

### 🔍 Exercise 1: Wallet Tracker (5 min)

Write a program that asks the user to enter how much money they want to add and how much they want to spend. Then calculate and print the remaining amount in the wallet.

**Requirements:**

- Use `+=` and `=` operators
- Start wallet balance from 0

### **Example Output:**

```c
Enter money to add: 1234
Enter money to spend: 100
Remaining: 1134
```

---

## 🟨 Part 2: Increment / Decrement & Modulus

### 🧠 Concept

- `++`, `-` for counter operations
- `%` for remainder, odd/even, digit extraction

### 🧪 Example 1: Count Up

```c
#include <stdio.h>

int main(void) {
    int count = 0;
    count++;
    count++;
    printf("Count: %d\n", count);
    return 0;
}
```

### **🧪 Example 2: Even/Odd Counter**

```c
#include <stdio.h>

int main(void)
{
    int num, even = 0, odd = 0;
    int count = 0;

    printf("Enter 5 numbers:\n");

    while (count < 5)
    {
        scanf("%d", &num);
        even += (num % 2 == 0);
        odd += (num % 2 != 0);
        count++;
    }

    printf("Even numbers: %d\n", even);
    printf("Odd numbers: %d\n", odd);
    return 0;
}
```

### 🔍 Exercise 2: Last Digit Extractor (10 min)

Write a program that asks the user to enter an integer number, then prints the last digit of that number using the modulus operator.

**Requirements:**

- Use `%` to extract the last digit
- Assume the user enters a valid integer

### **Example Output:**

```c
Enter a number: 2398
Last digit: 8
```

---

## 🟧 Part 3: Operator Precedence

### 🧠 Concept

- Operator precedence affects evaluation order
- Use parentheses to control execution

### 🧪 Example: Precedence Comparison

```c
#include <stdio.h>

int main(void) {
    int result1 = 2 + 3 * 4;
    int result2 = (2 + 3) * 4;
    printf("Without parentheses: %d\n", result1); // 14
    printf("With parentheses: %d\n", result2);     // 20
    return 0;
}
```

### 🔍 Exercise 3: Score Calculation (5 min)

Write a program to calculate a score in two ways:

1. Without parentheses: `base + bonus * level`
2. With parentheses: `(base + bonus) * level` Compare the results and explain why they are different.

**Requirements:**

- Use `int` variables
- Use , `+`, and parentheses
- Show both calculations in output

### **Example Output:**

```c
Score1: 160
Score2: 360
```

---

## 🟩 Part 4: While Loop

### 🧠 Concept

- Repeat a block while a condition is true
- Loop control with counter

### 🧪 Example 1: Multiplication Table

```c
#include <stdio.h>

int main(void) {
    int n, i = 1;
    printf("Enter a number: ");
    scanf("%d", &n);
    while (i <= 9) {
        printf("%d x %d = %d\n", n, i, n * i);
        i++;
    }
    return 0;
}
```

### **🧪 Example 2: Factorial Calculator**

```c
#include <stdio.h>

int main(void) {
    int n, result = 1, i = 1;
    printf("Enter a number: ");
    scanf("%d", &n);
    while (i <= n) {
        result *= i;
        i++;
    }
    printf("%d! = %d\n", n, result);
    return 0;
}
```

### 🔍 Exercise 4: Countdown (5 min)

Write a program that asks the user to input a number, and then prints numbers from that number down to 1 using a while loop.

**Requirements:**

- Use a `while` loop
- Start from the input number and print down to 1
- Use the `--` operator

### **Example Output:**

```c
Enter a number to countdown from: 14
14
13
12
11
10
9
8
7
6
5
4
3
2
1
```

---

## 🟪 Part 5: Do-While Loop & Input-Based Loops

### 🧠 Concept

- `do-while` ensures at least one execution
- Useful for input validation or repeated tasks

### 🧪 Example: Sum Until Negative

```c
#include <stdio.h>

int main(void) {
    int num;
    int sum = 0, count = 0;

    do {
        printf("Enter a non-negative number: ");
        scanf("%d", &num);

        sum += (num >= 0) * num;
        count += (num >= 0);
    } while (num >= 0);

    printf("You entered %d non-negative numbers.\n", count);
    printf("Their sum is %d.\n", sum);

    return 0;
}
```

### 🔍 **Exercise 5: Highest and Lowest Score Finder (10 min)**

Write a program that repeatedly asks the user to enter scores.

The loop stops when the user enters a **negative number**.

At the end, the program prints the **highest** and **lowest** scores entered.

### **Requirements**

- Use a `do-while` loop
- Do **not** use `if` statements
- Use logical expressions (e.g. `(score > max) * score + ...`)
- Track the total number of scores entered

### **Example Output:**

```c
Enter a score (negative to stop): 203
Enter a score (negative to stop): 120
Enter a score (negative to stop): 1240
Enter a score (negative to stop): 1203210
Enter a score (negative to stop): 2103100
Enter a score (negative to stop): 293
Enter a score (negative to stop): -3
You entered 6 scores.
Highest score: 210310
```

---
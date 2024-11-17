---
canonical: "https://jsandtsmastery.com/3/5/4"
title: "JavaScript Operators and Expressions: Mastering Arithmetic, Assignment, Comparison, and Logical Operators"
description: "Explore JavaScript operators and expressions, including arithmetic, assignment, comparison, and logical operators. Learn operator precedence and the differences between '==' and '==='."
linkTitle: "5.4 Operators and Expressions"
categories:
- JavaScript
- Web Development
- Programming Basics
tags:
- JavaScript
- Operators
- Expressions
- Coding
- Web Development
date: 2024-10-25
type: docs
nav_weight: 5400
license: "© 2024 Tokenizer Inc. CC BY-NC-SA 4.0"
---

## 5.4 Operators and Expressions

In this section, we will delve into the world of operators and expressions in JavaScript. Operators are symbols that perform operations on variables and values, while expressions are combinations of values, variables, and operators that compute a value. Understanding these concepts is crucial for writing effective and efficient JavaScript code.

### Common Operators and Their Functions

JavaScript provides a variety of operators, each serving a unique purpose. Let's explore some of the most common ones:

#### Arithmetic Operators

Arithmetic operators are used to perform mathematical operations:

- **Addition (`+`)**: Adds two numbers.
- **Subtraction (`-`)**: Subtracts the second number from the first.
- **Multiplication (`*`)**: Multiplies two numbers.
- **Division (`/`)**: Divides the first number by the second.
- **Modulus (`%`)**: Returns the remainder of a division.
- **Increment (`++`)**: Increases a number by one.
- **Decrement (`--`)**: Decreases a number by one.

**Example:**

```javascript
let a = 10;
let b = 5;

console.log(a + b); // Output: 15
console.log(a - b); // Output: 5
console.log(a * b); // Output: 50
console.log(a / b); // Output: 2
console.log(a % b); // Output: 0

a++;
console.log(a); // Output: 11

b--;
console.log(b); // Output: 4
```

#### Assignment Operators

Assignment operators are used to assign values to variables:

- **Assignment (`=`)**: Assigns a value to a variable.
- **Addition assignment (`+=`)**: Adds a value to a variable.
- **Subtraction assignment (`-=`)**: Subtracts a value from a variable.
- **Multiplication assignment (`*=`)**: Multiplies a variable by a value.
- **Division assignment (`/=`)**: Divides a variable by a value.
- **Modulus assignment (`%=`)**: Assigns the remainder of a division to a variable.

**Example:**

```javascript
let x = 10;

x += 5; // Equivalent to x = x + 5
console.log(x); // Output: 15

x -= 3; // Equivalent to x = x - 3
console.log(x); // Output: 12

x *= 2; // Equivalent to x = x * 2
console.log(x); // Output: 24

x /= 4; // Equivalent to x = x / 4
console.log(x); // Output: 6

x %= 2; // Equivalent to x = x % 2
console.log(x); // Output: 0
```

#### Comparison Operators

Comparison operators are used to compare two values:

- **Equal to (`==`)**: Checks if two values are equal.
- **Not equal to (`!=`)**: Checks if two values are not equal.
- **Strict equal to (`===`)**: Checks if two values are equal and of the same type.
- **Strict not equal to (`!==`)**: Checks if two values are not equal or not of the same type.
- **Greater than (`>`)**: Checks if the left value is greater than the right.
- **Less than (`<`)**: Checks if the left value is less than the right.
- **Greater than or equal to (`>=`)**: Checks if the left value is greater than or equal to the right.
- **Less than or equal to (`<=`)**: Checks if the left value is less than or equal to the right.

**Example:**

```javascript
let num1 = 10;
let num2 = "10";

console.log(num1 == num2); // Output: true
console.log(num1 === num2); // Output: false

console.log(num1 != num2); // Output: false
console.log(num1 !== num2); // Output: true

console.log(num1 > 5); // Output: true
console.log(num1 < 5); // Output: false
console.log(num1 >= 10); // Output: true
console.log(num1 <= 10); // Output: true
```

#### Logical Operators

Logical operators are used to combine multiple conditions:

- **Logical AND (`&&`)**: Returns true if both operands are true.
- **Logical OR (`||`)**: Returns true if at least one operand is true.
- **Logical NOT (`!`)**: Inverts the truth value of the operand.

**Example:**

```javascript
let isAdult = true;
let hasLicense = false;

console.log(isAdult && hasLicense); // Output: false
console.log(isAdult || hasLicense); // Output: true
console.log(!isAdult); // Output: false
```

### Expressions Using Operators

Expressions are combinations of values, variables, and operators that evaluate to a single value. They form the building blocks of JavaScript code.

#### Simple Expressions

A simple expression might involve a single arithmetic operation:

```javascript
let sum = 5 + 3; // Expression evaluates to 8
```

#### Complex Expressions

Complex expressions involve multiple operators and can include function calls:

```javascript
let result = (10 + 5) * (2 - 1); // Expression evaluates to 15
```

### Operator Precedence

Operator precedence determines the order in which operations are performed in an expression. Operators with higher precedence are evaluated before those with lower precedence.

#### Precedence Table

Here is a simplified table of operator precedence in JavaScript:

| Precedence | Operator Type       | Operators                  |
|------------|---------------------|----------------------------|
| Highest    | Grouping            | `()`                       |
|            | Member Access       | `.` `[]`                   |
|            | Function Call       | `()`                       |
|            | Increment/Decrement | `++` `--`                  |
|            | Unary               | `+` `-` `!` `typeof` `++` `--` |
|            | Multiplicative      | `*` `/` `%`                |
|            | Additive            | `+` `-`                    |
|            | Relational          | `<` `<=` `>` `>=`          |
|            | Equality            | `==` `!=` `===` `!==`      |
|            | Logical AND         | `&&`                       |
|            | Logical OR          | `||`                       |
| Lowest     | Assignment          | `=` `+=` `-=` `*=` `/=` `%=` |

#### Example of Operator Precedence

Consider the following expression:

```javascript
let result = 10 + 5 * 2; // Output: 20
```

In this expression, multiplication (`*`) has a higher precedence than addition (`+`), so `5 * 2` is evaluated first, resulting in `10 + 10`, which equals `20`.

### Difference Between `==` and `===`

In JavaScript, `==` and `===` are used for comparison, but they behave differently:

- **`==` (Equality Operator)**: Compares two values for equality, performing type conversion if necessary.
- **`===` (Strict Equality Operator)**: Compares two values for equality without performing type conversion.

**Example:**

```javascript
let num = 10;
let str = "10";

console.log(num == str);  // Output: true (type conversion occurs)
console.log(num === str); // Output: false (no type conversion)
```

### Practice Problems

To reinforce your understanding of operators and expressions, try solving these practice problems:

1. **Arithmetic Challenge**: Calculate the area of a rectangle with a width of 8 and a height of 5 using arithmetic operators.

2. **Comparison Puzzle**: Determine if the string `"100"` is equal to the number `100` using both `==` and `===` operators. Explain the difference in results.

3. **Logical Conundrum**: Write an expression that checks if a person is eligible to vote (age >= 18) and is a registered voter.

4. **Operator Precedence**: Evaluate the expression `5 + 3 * 2 - 4 / 2` and explain the order of operations.

5. **Assignment Twist**: Use assignment operators to double a variable's value and then subtract 10 from it.

### Try It Yourself

Experiment with the code examples provided in this section. Modify the values and operators to see how the results change. This hands-on practice will solidify your understanding of operators and expressions in JavaScript.

### Visual Aids

To better understand operator precedence, refer to the following flowchart that illustrates the order of operations:

```mermaid
graph TD;
    A[Start] --> B[Grouping ()];
    B --> C[Member Access . []];
    C --> D[Function Call ()];
    D --> E[Increment/Decrement ++ --];
    E --> F[Unary + - ! typeof];
    F --> G[Multiplicative * / %];
    G --> H[Additive + -];
    H --> I[Relational < <= > >=];
    I --> J[Equality == != === !==];
    J --> K[Logical AND &&];
    K --> L[Logical OR ||];
    L --> M[Assignment = += -= *= /= %=];
    M --> N[End];
```

### Key Takeaways

- **Operators** are symbols that perform operations on variables and values.
- **Expressions** are combinations of values, variables, and operators that compute a value.
- **Operator precedence** determines the order in which operations are performed.
- **`==` and `===`** are used for comparison, with `===` being stricter as it does not perform type conversion.

By mastering operators and expressions, you will be well-equipped to write more complex and efficient JavaScript code. Practice regularly and experiment with different combinations to deepen your understanding.

## Quiz Time!

{{< quizdown >}}

### Which operator is used to add two numbers in JavaScript?

- [x] +
- [ ] -
- [ ] *
- [ ] /

> **Explanation:** The `+` operator is used to add two numbers in JavaScript.

### What does the `===` operator do?

- [x] Compares two values for equality without type conversion
- [ ] Compares two values for equality with type conversion
- [ ] Assigns a value to a variable
- [ ] Performs arithmetic addition

> **Explanation:** The `===` operator compares two values for equality without performing type conversion.

### Which operator has the highest precedence?

- [x] ()
- [ ] *
- [ ] +
- [ ] ==

> **Explanation:** The grouping operator `()` has the highest precedence, ensuring that expressions within parentheses are evaluated first.

### What is the result of `5 + 3 * 2`?

- [x] 11
- [ ] 16
- [ ] 21
- [ ] 10

> **Explanation:** The multiplication operator `*` has higher precedence than addition `+`, so `3 * 2` is evaluated first, resulting in `5 + 6`, which equals `11`.

### How do you increment a variable by one?

- [x] ++
- [ ] --
- [ ] +=
- [ ] -=

> **Explanation:** The increment operator `++` increases a variable's value by one.

### What does the `!=` operator check?

- [x] If two values are not equal
- [ ] If two values are equal
- [ ] If a value is greater than another
- [ ] If a value is less than another

> **Explanation:** The `!=` operator checks if two values are not equal.

### Which operator is used to combine multiple conditions?

- [x] &&
- [ ] ||
- [ ] !
- [ ] ==

> **Explanation:** The logical AND operator `&&` is used to combine multiple conditions.

### What is the result of `10 % 3`?

- [x] 1
- [ ] 0
- [ ] 3
- [ ] 10

> **Explanation:** The modulus operator `%` returns the remainder of the division `10 / 3`, which is `1`.

### What does the `!` operator do?

- [x] Inverts the truth value of the operand
- [ ] Adds two numbers
- [ ] Multiplies two numbers
- [ ] Divides two numbers

> **Explanation:** The logical NOT operator `!` inverts the truth value of the operand.

### True or False: The `==` operator performs type conversion.

- [x] True
- [ ] False

> **Explanation:** The `==` operator performs type conversion, comparing values for equality after converting them to a common type.

{{< /quizdown >}}

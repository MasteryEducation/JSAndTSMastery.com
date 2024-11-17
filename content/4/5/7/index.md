---
canonical: "https://jsandtsmastery.com/4/5/7"
title: "Type Checking Primitives in JavaScript: Understanding the `typeof` Operator"
description: "Explore how to determine the type of primitive values in JavaScript using the `typeof` operator. Learn about its quirks and reliable methods for type checking."
linkTitle: "5.7. Type Checking Primitives"
categories:
- JavaScript
- Programming
- Web Development
tags:
- JavaScript
- Type Checking
- Primitives
- typeof
- Data Types
date: 2024-10-25
type: docs
nav_weight: 5700
license: "© 2024 Tokenizer Inc. CC BY-NC-SA 4.0"
---

## 5.7. Type Checking Primitives

In JavaScript, understanding the type of data you are working with is crucial for writing robust and error-free code. JavaScript is a dynamically typed language, meaning that variables can hold values of any type without any explicit declaration of the type. This flexibility, while powerful, can sometimes lead to unexpected behavior. Therefore, it's important to know how to check the type of a value, especially when dealing with primitive data types.

### Understanding the `typeof` Operator

The `typeof` operator is a built-in JavaScript operator that returns a string indicating the type of the unevaluated operand. It is a simple yet powerful tool for type checking, especially when dealing with primitive data types. The syntax is straightforward:

```javascript
typeof operand
```

Here, `operand` can be any expression whose type you want to determine. The `typeof` operator can be used with or without parentheses, like `typeof(operand)`, but the parentheses are optional.

### Primitive Data Types in JavaScript

Before diving into examples, let's briefly recap the primitive data types in JavaScript:

1. **Number**: Represents both integer and floating-point numbers.
2. **String**: Represents a sequence of characters.
3. **Boolean**: Represents a logical entity and can have two values: `true` and `false`.
4. **Undefined**: A variable that has been declared but not assigned a value.
5. **Null**: Represents the intentional absence of any object value.
6. **Symbol**: A unique and immutable primitive value, introduced in ECMAScript 6.
7. **BigInt**: Represents whole numbers larger than the `Number` type can safely represent, introduced in ECMAScript 2020.

### Using `typeof` with Primitive Data Types

Let's explore how the `typeof` operator works with each of these primitive data types through examples.

#### Number Type

The `typeof` operator returns `'number'` for any numeric value, whether it's an integer or a floating-point number.

```javascript
let integer = 42;
console.log(typeof integer); // 'number'

let float = 3.14;
console.log(typeof float); // 'number'
```

#### String Type

For strings, `typeof` returns `'string'`.

```javascript
let text = "Hello, World!";
console.log(typeof text); // 'string'
```

#### Boolean Type

For boolean values, `typeof` returns `'boolean'`.

```javascript
let isJavaScriptFun = true;
console.log(typeof isJavaScriptFun); // 'boolean'
```

#### Undefined Type

If a variable is declared but not assigned a value, `typeof` returns `'undefined'`.

```javascript
let notAssigned;
console.log(typeof notAssigned); // 'undefined'
```

#### Null Type

Here's where things get a bit quirky. Although `null` is a primitive value that represents the absence of any value, `typeof null` returns `'object'`. This is a well-known peculiarity in JavaScript, a remnant from its early days.

```javascript
let emptyValue = null;
console.log(typeof emptyValue); // 'object'
```

#### Symbol Type

For symbols, `typeof` returns `'symbol'`.

```javascript
let uniqueKey = Symbol('key');
console.log(typeof uniqueKey); // 'symbol'
```

#### BigInt Type

For BigInt values, `typeof` returns `'bigint'`.

```javascript
let largeNumber = BigInt(9007199254740991);
console.log(typeof largeNumber); // 'bigint'
```

### Quirks and Considerations

As we saw with `null`, the `typeof` operator has some quirks. Let's discuss these in more detail and suggest reliable methods for type checking.

#### The `typeof null` Quirk

The `typeof` operator returning `'object'` for `null` is a historical bug in JavaScript. Despite being a primitive type, `null` is treated as an object. This can lead to confusion, especially for beginners. To reliably check for `null`, use strict equality:

```javascript
let value = null;
console.log(value === null); // true
```

#### Arrays and Functions

While arrays and functions are technically objects, `typeof` treats them differently:

- For arrays, `typeof` returns `'object'`.
- For functions, `typeof` returns `'function'`.

```javascript
let array = [1, 2, 3];
console.log(typeof array); // 'object'

let func = function() {};
console.log(typeof func); // 'function'
```

To check if a value is an array, use `Array.isArray()`:

```javascript
console.log(Array.isArray(array)); // true
```

### Reliable Methods for Type Checking

While `typeof` is useful, it has limitations. Here are some additional methods for more reliable type checking:

#### Using `instanceof`

The `instanceof` operator tests whether an object is an instance of a specific constructor. It is useful for checking complex data types like arrays and custom objects.

```javascript
console.log(array instanceof Array); // true
console.log(func instanceof Function); // true
```

#### Using `Object.prototype.toString`

For a more consistent type check, use `Object.prototype.toString.call()`:

```javascript
console.log(Object.prototype.toString.call(array)); // '[object Array]'
console.log(Object.prototype.toString.call(func)); // '[object Function]'
```

This method returns a string that accurately represents the type of the object, including distinguishing between `null` and `undefined`.

### Try It Yourself

To deepen your understanding, try modifying the examples above. For instance, create variables of different types and use `typeof` to check their types. Experiment with arrays and functions to see how `typeof` behaves.

### Visualizing Type Checking with `typeof`

To better understand how the `typeof` operator interacts with different data types, let's visualize the process using a flowchart.

```mermaid
graph TD;
    A[Start] --> B{Is it a primitive type?}
    B -->|Yes| C[Use typeof]
    B -->|No| D{Is it an array or function?}
    D -->|Array| E[Use Array.isArray()]
    D -->|Function| F[Use typeof]
    D -->|Neither| G[Use instanceof or Object.prototype.toString]
    C --> H[Get type as string]
    E --> H
    F --> H
    G --> H
    H --> I[End]
```

This flowchart outlines the decision-making process when determining the type of a value in JavaScript, helping you choose the appropriate method for type checking.

### Key Takeaways

- The `typeof` operator is a quick way to check the type of a value in JavaScript, especially for primitive types.
- Be aware of quirks, such as `typeof null` returning `'object'`.
- Use additional methods like `instanceof` and `Object.prototype.toString` for more reliable type checking, especially for non-primitive types.

### Embrace the Journey

Remember, understanding data types and type checking is a fundamental skill in JavaScript. As you continue to learn and experiment, you'll become more adept at writing robust and efficient code. Keep practicing, stay curious, and enjoy the journey of mastering JavaScript!

## Quiz Time!

{{< quizdown >}}

### What does `typeof` return for a number?

- [x] 'number'
- [ ] 'integer'
- [ ] 'float'
- [ ] 'numeric'

> **Explanation:** `typeof` returns 'number' for both integers and floating-point numbers.

### What is the output of `typeof "Hello"`?

- [x] 'string'
- [ ] 'text'
- [ ] 'character'
- [ ] 'word'

> **Explanation:** `typeof` returns 'string' for any string value.

### How do you check if a value is `null`?

- [x] value === null
- [ ] typeof value === 'null'
- [ ] value == undefined
- [ ] typeof value === 'object'

> **Explanation:** Use strict equality `value === null` to check if a value is `null`.

### What does `typeof` return for an array?

- [ ] 'array'
- [ ] 'list'
- [x] 'object'
- [ ] 'collection'

> **Explanation:** `typeof` returns 'object' for arrays, as they are technically objects in JavaScript.

### Which method is reliable for checking if a value is an array?

- [ ] typeof value === 'array'
- [x] Array.isArray(value)
- [ ] value instanceof Array
- [ ] Object.prototype.toString.call(value) === '[object Array]'

> **Explanation:** `Array.isArray(value)` is a reliable method to check if a value is an array.

### What does `typeof` return for a function?

- [x] 'function'
- [ ] 'callable'
- [ ] 'method'
- [ ] 'object'

> **Explanation:** `typeof` returns 'function' for any function.

### What is the output of `typeof undefined`?

- [x] 'undefined'
- [ ] 'null'
- [ ] 'void'
- [ ] 'empty'

> **Explanation:** `typeof` returns 'undefined' for a variable that has not been assigned a value.

### What is the quirk of `typeof null`?

- [x] It returns 'object'
- [ ] It returns 'null'
- [ ] It returns 'undefined'
- [ ] It returns 'empty'

> **Explanation:** Due to a historical bug, `typeof null` returns 'object'.

### Which operator can be used to check if a value is an instance of a specific constructor?

- [x] instanceof
- [ ] typeof
- [ ] Object.prototype.toString
- [ ] Array.isArray

> **Explanation:** The `instanceof` operator checks if a value is an instance of a specific constructor.

### True or False: `typeof` can distinguish between different object types.

- [ ] True
- [x] False

> **Explanation:** `typeof` cannot distinguish between different object types; it returns 'object' for all objects except functions.

{{< /quizdown >}}

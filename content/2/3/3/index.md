---
canonical: "https://jsandtsmastery.com/2/3/3"
title: "Understanding Hoisting in TypeScript: A Beginner's Guide"
description: "Explore the concept of hoisting in TypeScript, how it affects variable and function declarations, and learn best practices to avoid common pitfalls."
linkTitle: "3.3 Hoisting in TypeScript"
categories:
- TypeScript
- JavaScript
- Programming
tags:
- Hoisting
- TypeScript
- JavaScript
- Variables
- Functions
date: 2024-10-25
type: docs
nav_weight: 3300
license: "© 2024 Tokenizer Inc. CC BY-NC-SA 4.0"
---

## 3.3 Hoisting in TypeScript

In this section, we will delve into the concept of hoisting in TypeScript, a feature inherited from JavaScript. Understanding hoisting is crucial for writing predictable and bug-free code. We will explore how hoisting works with different types of variable declarations and function declarations, and how TypeScript helps mitigate some of the common issues associated with hoisting.

### What is Hoisting?

Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their containing scope during the compile phase. This means that you can use variables and functions before they are actually declared in your code. However, only the declarations are hoisted, not the initializations.

#### Hoisting with `var` Declarations

In JavaScript, variables declared with `var` are hoisted to the top of their function or global scope. This can lead to unexpected behavior if you're not careful.

```typescript
console.log(myVar); // Output: undefined
var myVar = 5;
console.log(myVar); // Output: 5
```

In the example above, the declaration `var myVar` is hoisted to the top, but the initialization `myVar = 5` is not. Therefore, the first `console.log` outputs `undefined`.

#### Hoisting with Function Declarations

Function declarations are also hoisted, allowing you to call a function before it's defined in the code.

```typescript
console.log(add(2, 3)); // Output: 5

function add(a: number, b: number): number {
    return a + b;
}
```

Here, the function `add` is hoisted, so it can be called before its declaration.

### Hoisting with `let` and `const`

Unlike `var`, variables declared with `let` and `const` are not initialized until their declaration is evaluated. This means they are hoisted to the top of their block scope but are not accessible until the code execution reaches their declaration. This is known as the "temporal dead zone."

```typescript
console.log(myLet); // Error: Cannot access 'myLet' before initialization
let myLet = 10;
```

#### Temporal Dead Zone

The temporal dead zone (TDZ) is the time between the hoisting of a variable and its declaration. During this period, accessing the variable will result in a `ReferenceError`.

```typescript
function example() {
    console.log(myConst); // Error: Cannot access 'myConst' before initialization
    const myConst = 20;
}
```

### Best Practices to Avoid Hoisting Confusion

1. **Use `let` and `const`**: Prefer `let` and `const` over `var` to avoid hoisting-related issues. They provide block scope and prevent accidental re-declarations.

2. **Declare Variables at the Top**: Always declare your variables at the top of their scope to make their hoisting behavior explicit and your code more readable.

3. **Initialize Variables**: Initialize variables at the time of declaration to avoid undefined values.

4. **Use Functions Before Declaration Sparingly**: While function hoisting allows calling functions before their declaration, it's generally better to declare functions before calling them for better readability.

### Visualizing Hoisting

Let's visualize the hoisting process using a flowchart to better understand how TypeScript handles variable and function declarations.

```mermaid
flowchart TD
    A[Start] --> B[Declare var myVar]
    B --> C[Declare function add]
    C --> D[Initialize myVar = 5]
    D --> E[Call add(2, 3)]
    E --> F[End]

    subgraph Hoisting
    B
    C
    end
```

In this flowchart, `var` declarations and function declarations are hoisted to the top, while initializations occur in the order they appear in the code.

### Code Examples

Let's look at some practical examples to solidify our understanding of hoisting in TypeScript.

#### Example 1: Hoisting with `var`

```typescript
function hoistVar() {
    console.log(message); // Output: undefined
    var message = "Hello, TypeScript!";
    console.log(message); // Output: Hello, TypeScript!
}

hoistVar();
```

In this example, the `var` declaration is hoisted, but the initialization happens at the original line.

#### Example 2: Hoisting with `let`

```typescript
function hoistLet() {
    console.log(count); // Error: Cannot access 'count' before initialization
    let count = 10;
    console.log(count); // Output: 10
}

hoistLet();
```

Here, `let` prevents access to `count` before its declaration, resulting in an error.

#### Example 3: Function Hoisting

```typescript
function hoistFunction() {
    console.log(greet("World")); // Output: Hello, World!

    function greet(name: string): string {
        return `Hello, ${name}!`;
    }
}

hoistFunction();
```

The function `greet` is hoisted, allowing it to be called before its declaration.

### Try It Yourself

To better understand hoisting, try modifying the examples above:

- Change `var` to `let` or `const` and observe the differences in behavior.
- Move function declarations around and see how it affects the code execution.
- Experiment with initializing variables at different points in your code.

### Conclusion

Hoisting is a fundamental concept in JavaScript and TypeScript that affects how variables and functions are declared and initialized. By understanding hoisting, you can write more predictable and error-free code. Remember to use `let` and `const` to avoid common pitfalls associated with `var`, and always declare your variables and functions at the top of their scope.

### Additional Resources

For more information on hoisting and related topics, consider exploring the following resources:

- [MDN Web Docs: Hoisting](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting)
- [TypeScript Handbook: Variable Declarations](https://www.typescriptlang.org/docs/handbook/variable-declarations.html)

## Quiz Time!

{{< quizdown >}}

### What is hoisting?

- [x] A mechanism where variable and function declarations are moved to the top of their containing scope.
- [ ] A feature that prevents variables from being accessed before they are declared.
- [ ] A process of optimizing code execution by the TypeScript compiler.
- [ ] A method of declaring variables in TypeScript.

> **Explanation:** Hoisting is a JavaScript mechanism where variable and function declarations are moved to the top of their containing scope during the compile phase.

### Which of the following is true about `var` declarations?

- [x] They are hoisted to the top of their function or global scope.
- [ ] They are block-scoped and not hoisted.
- [ ] They cannot be re-declared in the same scope.
- [ ] They are initialized to `null` by default.

> **Explanation:** `var` declarations are hoisted to the top of their function or global scope, but their initializations are not.

### What happens if you try to access a `let` variable before its declaration?

- [ ] It returns `undefined`.
- [x] It throws a `ReferenceError`.
- [ ] It returns `null`.
- [ ] It initializes the variable to zero.

> **Explanation:** Accessing a `let` variable before its declaration results in a `ReferenceError` due to the temporal dead zone.

### How does hoisting affect function declarations?

- [x] Function declarations are hoisted, allowing them to be called before their declaration.
- [ ] Function declarations are not hoisted and must be declared before use.
- [ ] Function expressions are hoisted, but not function declarations.
- [ ] Functions declared with `const` are hoisted.

> **Explanation:** Function declarations are hoisted, meaning they can be called before their declaration in the code.

### What is the temporal dead zone?

- [x] The period between the hoisting of a variable and its declaration where it cannot be accessed.
- [ ] The time during which a variable is initialized to `undefined`.
- [ ] The period after a variable is declared but before it is initialized.
- [ ] The time when a variable is available globally.

> **Explanation:** The temporal dead zone is the period between the hoisting of a variable and its declaration where accessing it results in a `ReferenceError`.

### Which of the following is a best practice to avoid hoisting confusion?

- [x] Use `let` and `const` instead of `var`.
- [ ] Declare variables at the bottom of their scope.
- [ ] Avoid initializing variables at the time of declaration.
- [ ] Use function expressions instead of function declarations.

> **Explanation:** Using `let` and `const` helps avoid hoisting-related issues as they provide block scope and prevent accidental re-declarations.

### What is the output of the following code?

```typescript
console.log(foo);
var foo = "bar";
```

- [x] `undefined`
- [ ] `bar`
- [ ] `ReferenceError`
- [ ] `null`

> **Explanation:** The `var` declaration is hoisted, so `foo` is `undefined` at the time of the first `console.log`.

### How can you avoid temporal dead zone errors?

- [x] Declare and initialize variables at the top of their scope.
- [ ] Use `var` instead of `let` or `const`.
- [ ] Avoid using functions in your code.
- [ ] Declare variables after they are used.

> **Explanation:** Declaring and initializing variables at the top of their scope helps avoid temporal dead zone errors.

### Which of the following statements is true about `const` declarations?

- [x] They are block-scoped and not hoisted.
- [ ] They can be re-declared in the same scope.
- [ ] They are initialized to `undefined` by default.
- [ ] They are function-scoped like `var`.

> **Explanation:** `const` declarations are block-scoped and are not accessible before their declaration, similar to `let`.

### True or False: Hoisting allows you to use variables before they are declared.

- [x] True
- [ ] False

> **Explanation:** Hoisting allows you to use variables before they are declared, but only the declarations are hoisted, not the initializations.

{{< /quizdown >}}

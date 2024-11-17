---
canonical: "https://jsandtsmastery.com/4/7/4"

title: "Converting Values to Numbers in JavaScript: Techniques and Best Practices"
description: "Explore techniques for converting values to numbers in JavaScript, including the use of Number(), parseInt(), and parseFloat(). Learn about handling edge cases and invalid conversions."
linkTitle: "7.4. Converting to Number"
categories:
- JavaScript
- Programming
- Web Development
tags:
- JavaScript
- Type Conversion
- Number Conversion
- parseInt
- parseFloat
date: 2024-10-25
type: docs
nav_weight: 7400
license: "© 2024 Tokenizer Inc. CC BY-NC-SA 4.0"

---

## 7.4. Converting to Number

In JavaScript, converting values to numbers is a common task, especially when dealing with user input or data from external sources. This section will guide you through the various methods available for converting values to numbers, including `Number()`, `parseInt()`, and `parseFloat()`. We will also discuss the differences between these methods, provide examples with different data types, and highlight potential edge cases and how to handle invalid conversions.

### Understanding Number Conversion

Before diving into the specific methods for converting values to numbers, it's important to understand why this conversion is necessary. JavaScript is a dynamically typed language, meaning that variables can hold values of any type without explicit type declarations. However, certain operations require numeric values, such as mathematical calculations or comparisons. Therefore, converting values to numbers ensures that your code behaves as expected.

### Using `Number()`

The `Number()` function is a built-in JavaScript function that converts a given value to a number. It can handle a variety of input types, including strings, booleans, and date objects. Let's explore how `Number()` works with different types of input.

#### Converting Strings to Numbers

When converting strings to numbers, `Number()` attempts to parse the entire string as a numeric value. If the string contains valid numeric characters, it will return the corresponding number. Otherwise, it will return `NaN` (Not-a-Number).

```javascript
console.log(Number("42")); // Output: 42
console.log(Number("3.14")); // Output: 3.14
console.log(Number("42px")); // Output: NaN
console.log(Number("Hello")); // Output: NaN
```

#### Converting Booleans to Numbers

The `Number()` function converts `true` to `1` and `false` to `0`.

```javascript
console.log(Number(true)); // Output: 1
console.log(Number(false)); // Output: 0
```

#### Converting Date Objects to Numbers

When a date object is passed to `Number()`, it returns the number of milliseconds since January 1, 1970 (the Unix epoch).

```javascript
const date = new Date("2024-10-25");
console.log(Number(date)); // Output: 1729814400000 (value may vary)
```

### Using `parseInt()`

The `parseInt()` function parses a string and returns an integer. It can also handle strings with non-numeric characters, stopping the conversion at the first invalid character. Additionally, `parseInt()` can take a second argument, the radix, which specifies the base of the number system to use for conversion.

#### Basic Usage

```javascript
console.log(parseInt("42")); // Output: 42
console.log(parseInt("3.14")); // Output: 3
console.log(parseInt("42px")); // Output: 42
console.log(parseInt("Hello")); // Output: NaN
```

#### Using Radix

The radix parameter is crucial when dealing with numbers in different bases. For example, a binary number (base 2) can be converted using a radix of 2.

```javascript
console.log(parseInt("1010", 2)); // Output: 10
console.log(parseInt("FF", 16)); // Output: 255
```

### Using `parseFloat()`

The `parseFloat()` function parses a string and returns a floating-point number. Unlike `parseInt()`, it can handle decimal points and continues parsing until it encounters an invalid character.

```javascript
console.log(parseFloat("3.14")); // Output: 3.14
console.log(parseFloat("42.5px")); // Output: 42.5
console.log(parseFloat("Hello")); // Output: NaN
```

### Differences Between `Number()`, `parseInt()`, and `parseFloat()`

While all three functions can convert strings to numbers, they have distinct behaviors:

- **`Number()`**: Converts the entire string and returns `NaN` if any part is invalid.
- **`parseInt()`**: Stops parsing at the first invalid character and returns an integer.
- **`parseFloat()`**: Similar to `parseInt()`, but can handle decimals.

### Handling Edge Cases and Invalid Conversions

When converting values to numbers, it's essential to handle edge cases and invalid conversions gracefully. Here are some strategies:

#### Checking for `NaN`

Use the `isNaN()` function to check if a conversion resulted in `NaN`.

```javascript
const value = Number("Hello");
if (isNaN(value)) {
  console.log("Invalid number");
} else {
  console.log("Valid number:", value);
}
```

#### Providing Default Values

You can provide default values for invalid conversions using the logical OR (`||`) operator.

```javascript
const value = Number("Hello") || 0;
console.log(value); // Output: 0
```

#### Using `try...catch` for Error Handling

For more robust error handling, use a `try...catch` block to catch exceptions during conversion.

```javascript
try {
  const value = Number("Hello");
  if (isNaN(value)) {
    throw new Error("Invalid number");
  }
  console.log("Valid number:", value);
} catch (error) {
  console.error(error.message);
}
```

### Visualizing Number Conversion

To better understand how these conversion functions work, let's visualize the process using a flowchart.

```mermaid
flowchart TD
    A[Start] --> B{Input Value}
    B -->|String| C[Number()]
    B -->|String| D[parseInt()]
    B -->|String| E[parseFloat()]
    C --> F{Valid Number?}
    D --> G{Valid Integer?}
    E --> H{Valid Float?}
    F -->|Yes| I[Return Number]
    F -->|No| J[Return NaN]
    G -->|Yes| K[Return Integer]
    G -->|No| L[Return NaN]
    H -->|Yes| M[Return Float]
    H -->|No| N[Return NaN]
    I --> O[End]
    J --> O
    K --> O
    L --> O
    M --> O
    N --> O
```

### Try It Yourself

Now that we've covered the basics, try experimenting with the code examples. Modify the input values and observe how each function behaves. For instance, try converting different types of strings, such as hexadecimal numbers or scientific notation.

### References and Links

For further reading on number conversion in JavaScript, check out the following resources:

- [MDN Web Docs: Number()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)
- [MDN Web Docs: parseInt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt)
- [MDN Web Docs: parseFloat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat)

### Knowledge Check

Let's recap the key points from this section:

- Use `Number()` for general conversion, but be aware of its limitations with invalid strings.
- Use `parseInt()` and `parseFloat()` for more flexible parsing, especially when dealing with mixed strings.
- Always handle potential `NaN` results to avoid unexpected behavior in your code.

### Embrace the Journey

Remember, converting values to numbers is just one aspect of working with data in JavaScript. As you continue your learning journey, you'll encounter more complex scenarios and develop a deeper understanding of how JavaScript handles data. Keep experimenting, stay curious, and enjoy the process!

## Quiz Time!

{{< quizdown >}}

### Which function would you use to convert the string "42" to a number?

- [x] Number()
- [ ] parseInt()
- [ ] parseFloat()
- [ ] String()

> **Explanation:** The `Number()` function converts the entire string to a number, which is suitable for the string "42".

### What will `parseInt("42px")` return?

- [x] 42
- [ ] NaN
- [ ] 42.0
- [ ] "42"

> **Explanation:** `parseInt()` stops parsing at the first non-numeric character, so it returns 42.

### What does `Number("Hello")` return?

- [ ] 0
- [ ] "Hello"
- [x] NaN
- [ ] undefined

> **Explanation:** The `Number()` function returns `NaN` for strings that cannot be converted to a valid number.

### How does `parseFloat("3.14px")` handle the input?

- [x] It returns 3.14
- [ ] It returns NaN
- [ ] It returns 3
- [ ] It throws an error

> **Explanation:** `parseFloat()` parses the string until it encounters a non-numeric character, returning 3.14.

### What will `Number(true)` return?

- [x] 1
- [ ] 0
- [ ] NaN
- [ ] "true"

> **Explanation:** The `Number()` function converts `true` to 1.

### Which function can handle decimal points in strings?

- [ ] parseInt()
- [x] parseFloat()
- [ ] Number()
- [ ] Boolean()

> **Explanation:** `parseFloat()` can parse strings with decimal points.

### What is the radix parameter used for in `parseInt()`?

- [x] To specify the base of the number system
- [ ] To specify the precision of the number
- [ ] To specify the type of number
- [ ] To specify the length of the string

> **Explanation:** The radix parameter specifies the base of the number system (e.g., base 2 for binary).

### How can you check if a conversion resulted in `NaN`?

- [x] Use the `isNaN()` function
- [ ] Use the `typeof` operator
- [ ] Use the `instanceof` operator
- [ ] Use the `parseInt()` function

> **Explanation:** The `isNaN()` function checks if a value is `NaN`.

### What will `parseInt("1010", 2)` return?

- [x] 10
- [ ] 1010
- [ ] 2
- [ ] NaN

> **Explanation:** `parseInt("1010", 2)` converts the binary number 1010 to the decimal number 10.

### True or False: `Number()` can convert a date object to a number.

- [x] True
- [ ] False

> **Explanation:** `Number()` converts a date object to the number of milliseconds since January 1, 1970.

{{< /quizdown >}}

---
canonical: "https://jsandtsmastery.com/6/3/9"
title: "JavaScript Object.keys(), Object.values(), and Object.entries() Methods"
description: "Learn how to use Object.keys(), Object.values(), and Object.entries() to access and manipulate object data in JavaScript. Understand their differences and practical applications for cleaner, more efficient code."
linkTitle: "3.9 Object.keys(), Object.values(), and Object.entries()"
categories:
- JavaScript
- Object-Oriented Programming
- Web Development
tags:
- JavaScript
- Objects
- Object.keys()
- Object.values()
- Object.entries()
date: 2024-11-17
type: docs
nav_weight: 3900
license: "© 2024 Tokenizer Inc. CC BY-NC-SA 4.0"
---

## 3.9 Object.keys(), Object.values(), and Object.entries()

In this section, we will delve into three powerful methods provided by JavaScript to work with objects: `Object.keys()`, `Object.values()`, and `Object.entries()`. These methods are essential tools for accessing and manipulating object data, making your code cleaner and more efficient. As we explore each method, we'll provide practical examples and compare their outputs when used on the same object.

### Understanding Object.keys(), Object.values(), and Object.entries()

JavaScript objects are collections of key-value pairs. To effectively work with these collections, you need ways to access the keys, values, and entries. This is where `Object.keys()`, `Object.values()`, and `Object.entries()` come into play.

#### Object.keys()

The `Object.keys()` method returns an array of a given object's own enumerable property names, iterated in the same order that a normal loop would. This method is particularly useful when you need to iterate over an object's keys or when you want to know what keys are present in an object.

**Syntax:**

```javascript
Object.keys(obj)
```

- **Parameters**: `obj` - The object whose enumerable own properties are to be returned.
- **Return Value**: An array of strings representing the object's own enumerable property names.

**Example:**

```javascript
const car = {
  make: 'Toyota',
  model: 'Camry',
  year: 2020
};

const keys = Object.keys(car);
console.log(keys); // Output: ['make', 'model', 'year']
```

In this example, `Object.keys(car)` returns an array containing the keys of the `car` object.

#### Object.values()

The `Object.values()` method returns an array of a given object's own enumerable property values, in the same order as provided by a `for...in` loop. This method is useful when you need to work with the values of an object without concern for the keys.

**Syntax:**

```javascript
Object.values(obj)
```

- **Parameters**: `obj` - The object whose enumerable own property values are to be returned.
- **Return Value**: An array of the object's own enumerable property values.

**Example:**

```javascript
const car = {
  make: 'Toyota',
  model: 'Camry',
  year: 2020
};

const values = Object.values(car);
console.log(values); // Output: ['Toyota', 'Camry', 2020]
```

Here, `Object.values(car)` returns an array containing the values of the `car` object.

#### Object.entries()

The `Object.entries()` method returns an array of a given object's own enumerable string-keyed property `[key, value]` pairs. This method is useful when you need to work with both keys and values simultaneously.

**Syntax:**

```javascript
Object.entries(obj)
```

- **Parameters**: `obj` - The object whose enumerable own property `[key, value]` pairs are to be returned.
- **Return Value**: An array of the object's own enumerable string-keyed property `[key, value]` pairs.

**Example:**

```javascript
const car = {
  make: 'Toyota',
  model: 'Camry',
  year: 2020
};

const entries = Object.entries(car);
console.log(entries); // Output: [['make', 'Toyota'], ['model', 'Camry'], ['year', 2020]]
```

In this example, `Object.entries(car)` returns an array of arrays, each containing a key-value pair from the `car` object.

### Comparing Outputs

Let's compare the outputs of `Object.keys()`, `Object.values()`, and `Object.entries()` when used on the same object. This comparison will help you understand how each method provides a different perspective on the object's data.

```javascript
const person = {
  name: 'Alice',
  age: 30,
  occupation: 'Engineer'
};

console.log(Object.keys(person));   // Output: ['name', 'age', 'occupation']
console.log(Object.values(person)); // Output: ['Alice', 30, 'Engineer']
console.log(Object.entries(person)); // Output: [['name', 'Alice'], ['age', 30], ['occupation', 'Engineer']]
```

- **Object.keys()** gives us an array of the keys: `['name', 'age', 'occupation']`.
- **Object.values()** provides an array of the values: `['Alice', 30, 'Engineer']`.
- **Object.entries()** returns an array of key-value pairs: `[['name', 'Alice'], ['age', 30], ['occupation', 'Engineer']]`.

### Practical Uses

These methods are not just theoretical; they have practical applications in everyday coding tasks. Let's explore some scenarios where these methods can be particularly useful.

#### Iterating Over Object Properties

One common use case for these methods is iterating over an object's properties. This can be done using a `for...of` loop in combination with `Object.keys()`, `Object.values()`, or `Object.entries()`.

**Example: Iterating with Object.keys()**

```javascript
const user = {
  username: 'john_doe',
  email: 'john@example.com',
  role: 'admin'
};

for (const key of Object.keys(user)) {
  console.log(`${key}: ${user[key]}`);
}
// Output:
// username: john_doe
// email: john@example.com
// role: admin
```

**Example: Iterating with Object.values()**

```javascript
const user = {
  username: 'john_doe',
  email: 'john@example.com',
  role: 'admin'
};

for (const value of Object.values(user)) {
  console.log(value);
}
// Output:
// john_doe
// john@example.com
// admin
```

**Example: Iterating with Object.entries()**

```javascript
const user = {
  username: 'john_doe',
  email: 'john@example.com',
  role: 'admin'
};

for (const [key, value] of Object.entries(user)) {
  console.log(`${key}: ${value}`);
}
// Output:
// username: john_doe
// email: john@example.com
// role: admin
```

#### Transforming Objects

Another practical use of these methods is transforming objects. For instance, you might want to convert an object into a different format or structure.

**Example: Converting an Object to an Array of Strings**

```javascript
const product = {
  id: 101,
  name: 'Laptop',
  price: 899.99
};

const productArray = Object.entries(product).map(([key, value]) => `${key}: ${value}`);
console.log(productArray);
// Output: ['id: 101', 'name: Laptop', 'price: 899.99']
```

In this example, we use `Object.entries()` to convert the `product` object into an array of strings, each representing a key-value pair.

#### Filtering Object Properties

You can also use these methods to filter object properties based on certain criteria.

**Example: Filtering Properties by Value**

```javascript
const scores = {
  math: 85,
  science: 92,
  english: 78,
  history: 90
};

const highScores = Object.entries(scores)
  .filter(([subject, score]) => score > 80)
  .map(([subject]) => subject);

console.log(highScores); // Output: ['math', 'science', 'history']
```

Here, we use `Object.entries()` to filter the `scores` object, keeping only the subjects with scores greater than 80.

### Encouraging Cleaner Code

Using `Object.keys()`, `Object.values()`, and `Object.entries()` can lead to cleaner and more maintainable code. These methods provide a declarative way to access and manipulate object data, reducing the need for complex loops and conditionals.

**Example: Avoiding Nested Loops**

Consider a scenario where you need to compare two objects and find common keys. Using `Object.keys()` simplifies this task.

```javascript
const obj1 = { a: 1, b: 2, c: 3 };
const obj2 = { b: 4, c: 5, d: 6 };

const commonKeys = Object.keys(obj1).filter(key => key in obj2);
console.log(commonKeys); // Output: ['b', 'c']
```

In this example, we use `Object.keys()` and `filter()` to find common keys between `obj1` and `obj2`, avoiding the need for nested loops.

### Try It Yourself

Now that we've explored these methods, it's time to try them out yourself. Experiment with the following exercises to reinforce your understanding:

1. **Exercise 1**: Create an object representing a book with properties like `title`, `author`, and `year`. Use `Object.keys()`, `Object.values()`, and `Object.entries()` to display the keys, values, and entries of the object.

2. **Exercise 2**: Write a function that takes an object and returns an array of keys whose values are strings. Use `Object.entries()` to implement this function.

3. **Exercise 3**: Given two objects, write a function that returns a new object containing only the properties that exist in both objects. Use `Object.keys()` and `filter()` to achieve this.

### Visualizing Object Methods

To further enhance your understanding, let's visualize how these methods interact with an object using a diagram.

```mermaid
graph TD;
    A[Object] --> B[Object.keys()]
    A --> C[Object.values()]
    A --> D[Object.entries()]
    B --> E[Array of Keys]
    C --> F[Array of Values]
    D --> G[Array of Key-Value Pairs]
```

In this diagram, we see how an object is processed by `Object.keys()`, `Object.values()`, and `Object.entries()`, resulting in different arrays that represent the object's data.

### References and Further Reading

For more information on these methods, check out the following resources:

- [MDN Web Docs: Object.keys()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys)
- [MDN Web Docs: Object.values()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/values)
- [MDN Web Docs: Object.entries()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/entries)

### Knowledge Check

Before we wrap up, let's summarize the key takeaways:

- **Object.keys()** returns an array of an object's keys.
- **Object.values()** returns an array of an object's values.
- **Object.entries()** returns an array of an object's key-value pairs.
- These methods are useful for iterating over, transforming, and filtering object data.
- Using these methods can lead to cleaner and more maintainable code.

### Embrace the Journey

Remember, mastering these methods is just one step on your journey to becoming proficient in JavaScript. As you continue to learn, you'll discover even more powerful tools and techniques to enhance your coding skills. Keep experimenting, stay curious, and enjoy the process!

## Quiz Time!

{{< quizdown >}}

### What does Object.keys() return?

- [x] An array of the object's own enumerable property names.
- [ ] An array of the object's own enumerable property values.
- [ ] An array of the object's own enumerable property [key, value] pairs.
- [ ] A string representation of the object.

> **Explanation:** Object.keys() returns an array of the object's own enumerable property names, which are the keys of the object.

### What is the return value of Object.values()?

- [ ] An array of the object's own enumerable property names.
- [x] An array of the object's own enumerable property values.
- [ ] An array of the object's own enumerable property [key, value] pairs.
- [ ] A string representation of the object.

> **Explanation:** Object.values() returns an array of the object's own enumerable property values.

### Which method returns an array of [key, value] pairs?

- [ ] Object.keys()
- [ ] Object.values()
- [x] Object.entries()
- [ ] Object.toString()

> **Explanation:** Object.entries() returns an array of the object's own enumerable property [key, value] pairs.

### How can you iterate over an object's keys using Object.keys()?

- [x] Use a for...of loop with Object.keys().
- [ ] Use a for...in loop directly on the object.
- [ ] Use a while loop with Object.keys().
- [ ] Use a map function on the object.

> **Explanation:** You can use a for...of loop with Object.keys() to iterate over an object's keys.

### What is a practical use of Object.entries()?

- [x] Transforming an object into an array of key-value pairs.
- [ ] Converting an object to a string.
- [ ] Sorting an object's keys.
- [ ] Filtering an object's values.

> **Explanation:** Object.entries() is useful for transforming an object into an array of key-value pairs, which can then be manipulated or iterated over.

### Which method would you use to get all the values of an object?

- [ ] Object.keys()
- [x] Object.values()
- [ ] Object.entries()
- [ ] Object.getOwnPropertyNames()

> **Explanation:** Object.values() returns an array of all the values of an object's own enumerable properties.

### How can Object.keys() help in finding common keys between two objects?

- [x] By filtering the keys of one object to see if they exist in another.
- [ ] By comparing the values of both objects.
- [ ] By converting both objects to strings.
- [ ] By merging the objects.

> **Explanation:** Object.keys() can be used to filter the keys of one object to check if they exist in another, helping to find common keys.

### What is the output of Object.entries({ a: 1, b: 2 })?

- [ ] ['a', 'b']
- [ ] [1, 2]
- [x] [['a', 1], ['b', 2]]
- [ ] { a: 1, b: 2 }

> **Explanation:** Object.entries() returns an array of key-value pairs, so the output is [['a', 1], ['b', 2]].

### Can Object.values() be used to iterate over an object's keys?

- [ ] True
- [x] False

> **Explanation:** Object.values() returns an array of values, not keys, so it cannot be used to iterate over an object's keys.

### Using Object.entries(), how can you convert an object to an array of strings with key-value pairs?

- [x] Use map() on Object.entries() to format each pair.
- [ ] Use filter() on Object.entries() to format each pair.
- [ ] Use reduce() on Object.entries() to format each pair.
- [ ] Use forEach() on Object.entries() to format each pair.

> **Explanation:** You can use map() on the array returned by Object.entries() to format each key-value pair as a string.

{{< /quizdown >}}

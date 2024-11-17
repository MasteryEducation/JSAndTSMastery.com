---
canonical: "https://jsandtsmastery.com/6/3/2"

title: "Accessing and Modifying Properties in JavaScript Objects"
description: "Learn how to access and modify properties in JavaScript objects using dot and bracket notation, and understand when to use each."
linkTitle: "3.2 Accessing and Modifying Properties"
categories:
- JavaScript
- Object-Oriented Programming
- Web Development
tags:
- JavaScript Objects
- Dot Notation
- Bracket Notation
- Property Access
- Object Manipulation
date: 2024-11-17
type: docs
nav_weight: 3200
license: "© 2024 Tokenizer Inc. CC BY-NC-SA 4.0"
---

## 3.2 Accessing and Modifying Properties

In JavaScript, objects are a fundamental part of the language, serving as collections of properties. Each property is a key-value pair, where the key is a string (or a Symbol) and the value can be any data type, including other objects. Understanding how to access and modify these properties is crucial for working effectively with objects. In this section, we will explore how to read and change object properties using dot notation and bracket notation, and discuss when to use each method. We will also cover how to add, update, and delete properties, with examples using both primitive and reference property values.

### Accessing Properties

Accessing properties in JavaScript objects can be done using two main notations: dot notation and bracket notation. Each has its own use cases and benefits.

#### Dot Notation

Dot notation is the most common way to access properties. It is straightforward and easy to read. Here's how you can use dot notation to access a property:

```javascript
const person = {
  name: 'Alice',
  age: 30,
  job: 'Developer'
};

// Accessing properties using dot notation
console.log(person.name); // Output: Alice
console.log(person.age);  // Output: 30
```

**Advantages of Dot Notation:**

- **Readability**: Dot notation is concise and easy to understand.
- **Simplicity**: It is straightforward to use when the property name is a valid identifier (i.e., it does not contain spaces or special characters).

**Limitations of Dot Notation:**

- **Static Property Names**: Dot notation cannot be used if the property name is stored in a variable or if it contains special characters or spaces.

#### Bracket Notation

Bracket notation offers more flexibility than dot notation. It allows you to use variables to access property names and is necessary when dealing with property names that are not valid identifiers.

```javascript
const person = {
  'first name': 'Alice',
  age: 30,
  job: 'Developer'
};

// Accessing properties using bracket notation
console.log(person['first name']); // Output: Alice

// Using a variable to access a property
const propertyName = 'age';
console.log(person[propertyName]);  // Output: 30
```

**Advantages of Bracket Notation:**

- **Dynamic Property Names**: You can use variables or expressions to access properties.
- **Special Characters**: It allows access to properties with names that include spaces or special characters.

**When to Use Each Notation:**

- **Dot Notation**: Use when property names are known and are valid identifiers.
- **Bracket Notation**: Use when property names are dynamic, stored in variables, or contain special characters.

### Modifying Properties

Once you know how to access properties, modifying them is straightforward. You can add new properties, update existing ones, or delete them.

#### Adding and Updating Properties

Adding a new property or updating an existing one is done in the same way. If the property exists, its value is updated; if it doesn't, the property is added.

```javascript
const car = {
  brand: 'Toyota',
  model: 'Corolla'
};

// Adding a new property
car.year = 2020;
console.log(car.year); // Output: 2020

// Updating an existing property
car.model = 'Camry';
console.log(car.model); // Output: Camry
```

#### Deleting Properties

To remove a property from an object, use the `delete` operator. This operator removes the property and its value from the object.

```javascript
const book = {
  title: '1984',
  author: 'George Orwell',
  year: 1949
};

// Deleting a property
delete book.year;
console.log(book.year); // Output: undefined
```

**Note**: The `delete` operator only removes the property from the object. It does not affect any other references to the object.

### Working with Primitive and Reference Values

JavaScript properties can hold both primitive values (such as numbers and strings) and reference values (such as objects and arrays). Understanding how these values behave when accessed or modified is important.

#### Primitive Values

Primitive values are immutable, meaning their value cannot be changed. When you assign a primitive value to a property, you are copying the value.

```javascript
const user = {
  name: 'Bob',
  age: 25
};

// Primitive value assignment
let userName = user.name;
userName = 'Charlie';

console.log(user.name); // Output: Bob
```

In the example above, changing `userName` does not affect `user.name` because `userName` holds a copy of the primitive value.

#### Reference Values

Reference values, such as objects and arrays, are mutable and are accessed by reference. This means that when you assign a reference value to a property, you are assigning a reference to the original value, not a copy.

```javascript
const settings = {
  theme: 'dark',
  preferences: {
    notifications: true,
    language: 'en'
  }
};

// Reference value assignment
const userPreferences = settings.preferences;
userPreferences.language = 'fr';

console.log(settings.preferences.language); // Output: fr
```

In this example, changing `userPreferences.language` also changes `settings.preferences.language` because both variables reference the same object.

### Try It Yourself

Now that we've covered the basics, let's encourage you to experiment with the concepts:

1. **Create an Object**: Start by creating an object representing a book with properties like `title`, `author`, and `year`.

2. **Access Properties**: Use both dot and bracket notation to access the properties of your object.

3. **Modify Properties**: Add a new property `genre` and update the `year` property.

4. **Delete a Property**: Remove the `author` property from your object.

5. **Experiment with Reference Values**: Add a property that holds an array of reviews. Modify the array and observe the changes.

### Visualizing Property Access and Modification

To help you visualize how property access and modification work, let's use a diagram to represent an object and its properties.

```mermaid
graph TD;
    A[Object] --> B[Property: title]
    A --> C[Property: author]
    A --> D[Property: year]
    A --> E[Property: genre]
    A --> F[Property: reviews]

    B --> G[Value: '1984']
    C --> H[Value: 'George Orwell']
    D --> I[Value: 1949]
    E --> J[Value: 'Dystopian']
    F --> K[Array: ['Excellent', 'Thought-provoking']]
```

In this diagram, the object has several properties, each with its own value. The `reviews` property holds an array, which is a reference value.

### References and Links

For more information on JavaScript objects and property manipulation, you can refer to the following resources:

- [MDN Web Docs: Working with Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects)
- [W3Schools: JavaScript Objects](https://www.w3schools.com/js/js_objects.asp)

### Knowledge Check

Let's reinforce your understanding with some questions and exercises:

- **Question**: What is the difference between dot notation and bracket notation?
- **Exercise**: Create an object representing a movie and practice accessing and modifying its properties using both notations.

### Embrace the Journey

Remember, this is just the beginning of your journey with JavaScript objects. As you progress, you'll build more complex and interactive applications. Keep experimenting, stay curious, and enjoy the journey!

## Quiz Time!

{{< quizdown >}}

### Which notation is used to access properties with dynamic names?

- [ ] Dot notation
- [x] Bracket notation
- [ ] Both
- [ ] Neither

> **Explanation:** Bracket notation allows you to use variables or expressions to access properties with dynamic names.

### What happens if you try to access a non-existent property of an object?

- [ ] An error is thrown
- [x] `undefined` is returned
- [ ] `null` is returned
- [ ] The object is deleted

> **Explanation:** Accessing a non-existent property returns `undefined` without throwing an error.

### How do you delete a property from an object?

- [ ] Using the `remove` keyword
- [ ] Setting the property to `null`
- [x] Using the `delete` operator
- [ ] Using the `unset` keyword

> **Explanation:** The `delete` operator is used to remove a property from an object.

### Which of the following is a primitive value?

- [x] Number
- [ ] Object
- [ ] Array
- [ ] Function

> **Explanation:** Numbers are primitive values, whereas objects, arrays, and functions are reference values.

### Can you use dot notation to access a property with spaces in its name?

- [ ] Yes
- [x] No

> **Explanation:** Dot notation cannot be used with property names that contain spaces. Use bracket notation instead.

### What is the result of `console.log(person['age'])` if `person` is `{ name: 'Alice' }`?

- [ ] 0
- [ ] `null`
- [x] `undefined`
- [ ] An error is thrown

> **Explanation:** Since the `age` property does not exist in the `person` object, `undefined` is returned.

### Which of the following is a reference value?

- [ ] String
- [ ] Number
- [x] Array
- [ ] Boolean

> **Explanation:** Arrays are reference values, while strings, numbers, and booleans are primitive values.

### How do you add a new property to an object?

- [ ] Using the `add` keyword
- [x] Assigning a value to a new property name
- [ ] Using the `new` keyword
- [ ] Using the `create` method

> **Explanation:** You can add a new property by simply assigning a value to a new property name.

### What is the output of `console.log(car['brand'])` if `car` is `{ brand: 'Toyota', model: 'Corolla' }`?

- [x] `Toyota`
- [ ] `Corolla`
- [ ] `undefined`
- [ ] An error is thrown

> **Explanation:** The `brand` property exists in the `car` object, so its value, `Toyota`, is returned.

### True or False: Bracket notation can only be used with strings.

- [ ] True
- [x] False

> **Explanation:** Bracket notation can be used with strings, variables, or expressions to access properties.

{{< /quizdown >}}



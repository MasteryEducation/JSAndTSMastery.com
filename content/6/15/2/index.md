---
canonical: "https://jsandtsmastery.com/6/15/2"

title: "Glossary of Object-Oriented Programming Terminology in JavaScript"
description: "Explore essential Object-Oriented Programming terms and concepts in JavaScript, designed for beginners."
linkTitle: "Glossary of Object-Oriented Programming Terminology"
categories:
- JavaScript
- Object-Oriented Programming
- Programming Glossary
tags:
- JavaScript
- OOP
- Programming Terms
- Glossary
- Beginners
date: 2024-11-17
type: docs
nav_weight: 15200
license: "© 2024 Tokenizer Inc. CC BY-NC-SA 4.0"

---

## B. Glossary of Object-Oriented Programming Terminology

Welcome to the glossary of Object-Oriented Programming (OOP) terminology in JavaScript. This section is designed to provide you with clear and concise definitions of key terms and concepts that are essential for understanding OOP in JavaScript. Whether you're a beginner or looking to refresh your knowledge, this glossary will serve as a quick reference guide. Terms are listed alphabetically for easy navigation, and cross-references to relevant chapters or sections are included where applicable.

### A

**Abstraction**  
Abstraction is the concept of hiding the complex reality while exposing only the necessary parts. It helps in reducing programming complexity and effort. In JavaScript, abstraction can be achieved using functions, classes, and modules. For more details, refer to Chapter 6 on Encapsulation and Data Privacy.

**Abstract Class**  
An abstract class is a class that cannot be instantiated and is designed to be subclassed. It often contains one or more abstract methods that must be implemented by subclasses. JavaScript does not have built-in support for abstract classes, but they can be simulated using ES6 classes. See Chapter 7 for more on abstract classes and methods.

### B

**Binding**  
Binding refers to the association of a function with an object. In JavaScript, the `this` keyword is dynamically bound based on how a function is called. Understanding binding is crucial for working with methods in objects. See Chapter 2.5 for more on the `this` keyword.

**Built-in Objects**  
JavaScript provides several built-in objects like `Array`, `Date`, `Math`, etc., which come with predefined properties and methods. These objects are part of the JavaScript language core and are available in any environment where JavaScript runs. Explore Chapter 4.6 for more on built-in constructors and prototypes.

### C

**Class**  
A class is a blueprint for creating objects with specific properties and methods. Introduced in ES6, classes in JavaScript provide a more familiar syntax for creating objects and handling inheritance. For a detailed explanation, see Chapter 5 on ES6 Classes and Syntax.

**Closure**  
A closure is a function that retains access to its lexical scope even when the function is executed outside that scope. Closures are commonly used for data encapsulation and maintaining state. Learn more about closures in Chapter 2.7.

**Constructor**  
A constructor is a special method in a class that is called when an object is instantiated. It is used to initialize object properties. In JavaScript, constructors are defined using the `constructor` keyword. See Chapter 5.2 for more on class constructors.

**Composition**  
Composition is a design principle where objects are composed using other objects, rather than inheriting from a parent class. It is often preferred over inheritance for creating flexible and maintainable code. Chapter 7.8 discusses composition in detail.

### D

**Data Encapsulation**  
Data encapsulation is the practice of keeping the internal state of an object hidden from the outside world and only allowing access through public methods. This is a fundamental principle of OOP that helps in maintaining control over the data. See Chapter 6.1 for more on encapsulation.

**Delegation**  
Delegation is a design pattern where an object handles a request by passing it to a second delegate object. This pattern is often used to achieve code reuse and separation of concerns. Chapter 7.9 covers delegation patterns.

### E

**Encapsulation**  
Encapsulation is the bundling of data and methods that operate on the data within a single unit or class. It restricts direct access to some of an object's components, which can prevent the accidental modification of data. See Chapter 6 for a comprehensive look at encapsulation techniques.

**Extends**  
The `extends` keyword in JavaScript is used in class declarations or class expressions to create a class that is a child of another class. This is a part of the class-based inheritance model introduced in ES6. For more information, refer to Chapter 5.5 on inheritance.

### F

**Factory Function**  
A factory function is a function that returns a new object. Unlike constructor functions, factory functions do not use the `new` keyword. They offer a flexible way to create objects and can include logic to determine what kind of object to create. See Chapter 8.5 for more on the factory pattern.

### G

**Getter/Setter**  
Getters and setters are special methods that provide controlled access to an object's properties. They allow you to define how a property is accessed and modified. JavaScript supports getters and setters through the `get` and `set` keywords. Chapter 5.7 provides more details on using getters and setters.

### H

**Hoisting**  
Hoisting is JavaScript's default behavior of moving declarations to the top of the current scope. This means that variable and function declarations are processed before any code is executed. Understanding hoisting is crucial for avoiding common pitfalls. See Chapter 2.8 for more on hoisting.

### I

**Inheritance**  
Inheritance is a mechanism where one class can inherit properties and methods from another class. It is a fundamental feature of OOP that promotes code reuse. JavaScript supports both prototypal and class-based inheritance. Chapter 7 covers inheritance in depth.

**Instance**  
An instance is a specific realization of any object. In JavaScript, when a class is defined, no memory is allocated until an object is instantiated. Instances are created using the `new` keyword. For more on creating instances, see Chapter 4.2.

**Interface**  
An interface is a way to define a contract for classes without specifying the implementation details. JavaScript does not have built-in support for interfaces, but they can be simulated using classes and objects. Interfaces are often used to ensure that different classes adhere to a specific structure.

### J

**JSON (JavaScript Object Notation)**  
JSON is a lightweight data interchange format that is easy for humans to read and write, and easy for machines to parse and generate. It is based on a subset of JavaScript's object literal syntax. JSON is commonly used for transmitting data in web applications.

### K

**Keyword**  
A keyword is a reserved word in JavaScript that has a specific meaning and cannot be used as an identifier. Examples include `class`, `function`, `return`, and `var`. Understanding keywords is essential for writing syntactically correct JavaScript code.

### L

**Lexical Scope**  
Lexical scope is the scope defined by the physical arrangement of the code. In JavaScript, functions are lexically scoped, meaning that they can access variables from the scope in which they were defined. This is a key concept in understanding closures. See Chapter 2.7 for more on scope and closure.

### M

**Method**  
A method is a function that is a property of an object. Methods define the behavior of objects and can access and modify the object's properties. In JavaScript, methods are often defined within classes. Chapter 3.4 discusses methods in objects.

**Mixin**  
A mixin is a class that provides methods that can be used by other classes without being a parent class. Mixins are a way to achieve multiple inheritance in JavaScript. They allow for the reuse of code across different classes. See Chapter 7.7 for more on mixins.

### N

**Namespace**  
A namespace is a container that holds a set of identifiers and allows the organization of code into logical groups. JavaScript does not have built-in support for namespaces, but they can be simulated using objects and modules.

**New Operator**  
The `new` operator in JavaScript is used to create an instance of a user-defined object type or one of the built-in object types. It initializes the object and sets up the prototype chain. For more on the `new` operator, see Chapter 4.2.

### O

**Object**  
An object is a collection of properties and methods. In JavaScript, objects are the fundamental building blocks for modeling real-world entities. They can be created using object literals, constructors, or classes. Chapter 3 provides a detailed look at working with objects.

**Object-Oriented Programming (OOP)**  
OOP is a programming paradigm based on the concept of objects, which can contain data and code to manipulate that data. OOP principles include encapsulation, inheritance, and polymorphism. JavaScript is a multi-paradigm language that supports OOP. See Chapter 1.4 for an introduction to OOP.

### P

**Polymorphism**  
Polymorphism is the ability of different objects to be treated as instances of the same class through a common interface. It allows for the implementation of different methods that are called through the same interface. Chapter 7.5 covers method overriding and polymorphism.

**Prototype**  
A prototype is an object from which other objects inherit properties and methods. In JavaScript, every object has a prototype, and objects inherit from their prototype. Understanding prototypes is key to mastering JavaScript's inheritance model. See Chapter 4.4 for more on prototypes.

**Prototype Chain**  
The prototype chain is a series of links between objects that allows properties and methods to be inherited. When a property or method is accessed, JavaScript looks up the prototype chain to find it. Chapter 4.5 explains prototype inheritance in detail.

### Q

**Query Selector**  
The query selector is a method used to select DOM elements in JavaScript. It allows for the selection of elements using CSS selectors. Although not directly related to OOP, understanding DOM manipulation is essential for web development.

### R

**Refactoring**  
Refactoring is the process of restructuring existing code without changing its external behavior. It is often done to improve code readability, maintainability, and performance. Chapter 12.3 discusses refactoring code to use OOP.

**Return Statement**  
The return statement is used to exit a function and return a value to the caller. It is a fundamental part of function definitions in JavaScript.

### S

**Scope**  
Scope determines the accessibility of variables and functions in JavaScript. There are two types of scope: global and local. Understanding scope is crucial for managing variable visibility and avoiding conflicts. See Chapter 2.7 for more on scope.

**Static Method**  
A static method is a method that belongs to the class itself rather than an instance of the class. Static methods are often used for utility functions that do not require access to instance data. Chapter 5.4 covers static methods and properties.

**Super Keyword**  
The `super` keyword is used to call functions on an object's parent class. It is used in class-based inheritance to access and call functions on an object's parent. See Chapter 5.5 for more on inheritance with `extends` and `super`.

### T

**This Keyword**  
The `this` keyword refers to the object from which a function was called. It is dynamically scoped and can change based on how a function is invoked. Understanding `this` is essential for working with methods and constructors. See Chapter 2.5 for more on the `this` keyword.

**Type Coercion**  
Type coercion is the automatic or implicit conversion of values from one data type to another. JavaScript is a loosely typed language, and type coercion can lead to unexpected results if not handled carefully.

### U

**Undefined**  
`Undefined` is a primitive value automatically assigned to variables that have just been declared or to formal arguments for which there are no actual arguments. It is one of JavaScript's built-in data types.

### V

**Variable**  
A variable is a named storage for data. In JavaScript, variables can be declared using `var`, `let`, or `const`. Understanding variables and their scope is fundamental to programming in JavaScript. See Chapter 2.1 for more on variables and data types.

### W

**WeakMap**  
A `WeakMap` is a collection of key/value pairs where the keys are objects and the values can be arbitrary values. The keys in a `WeakMap` are weakly referenced, meaning they can be garbage collected if there are no other references to the object. See Chapter 6.3 for more on using `WeakMap` for data privacy.

**WeakSet**  
A `WeakSet` is similar to a `Set`, but the values are weakly held, meaning they can be garbage collected if there are no other references to the object. `WeakSet` is useful for keeping track of objects without preventing their garbage collection.

### X

**XMLHttpRequest**  
`XMLHttpRequest` is an API available in web browsers that allows for the sending and receiving of data between a web page and a server. Although not directly related to OOP, understanding how to make asynchronous requests is essential for modern web development.

### Y

**Yield**  
The `yield` keyword is used in generator functions to pause execution and return a value. It allows for the creation of iterators and is part of JavaScript's support for asynchronous programming.

### Z

**Zero-Based Indexing**  
Zero-based indexing is a way of numbering elements in an array where the first element is assigned an index of 0. This is the standard indexing method used in JavaScript arrays.

---

## Quiz Time!

{{< quizdown >}}

### What is encapsulation in Object-Oriented Programming?

- [x] The bundling of data and methods that operate on the data within a single unit
- [ ] The ability of different objects to be treated as instances of the same class
- [ ] The process of restructuring existing code without changing its external behavior
- [ ] The automatic conversion of values from one data type to another

> **Explanation:** Encapsulation is the bundling of data and methods that operate on the data within a single unit or class, which restricts direct access to some of an object's components.


### What does the `extends` keyword do in JavaScript?

- [x] It creates a class that is a child of another class
- [ ] It binds a function to an object
- [ ] It defines a new object type
- [ ] It converts values from one data type to another

> **Explanation:** The `extends` keyword in JavaScript is used in class declarations to create a class that is a child of another class, enabling inheritance.


### Which of the following is a characteristic of a closure?

- [x] It retains access to its lexical scope even when executed outside that scope
- [ ] It is a special method in a class called when an object is instantiated
- [ ] It is a function that returns a new object
- [ ] It is a method that belongs to the class itself rather than an instance

> **Explanation:** A closure is a function that retains access to its lexical scope even when the function is executed outside that scope.


### What is the purpose of the `super` keyword?

- [x] To call functions on an object's parent class
- [ ] To create a new instance of a class
- [ ] To define a method that belongs to the class itself
- [ ] To automatically convert values from one data type to another

> **Explanation:** The `super` keyword is used to call functions on an object's parent class, especially in class-based inheritance.


### Which of the following best describes polymorphism?

- [x] The ability of different objects to be treated as instances of the same class through a common interface
- [ ] The process of hiding the complex reality while exposing only the necessary parts
- [x] The implementation of different methods that are called through the same interface
- [ ] The bundling of data and methods that operate on the data within a single unit

> **Explanation:** Polymorphism is the ability of different objects to be treated as instances of the same class through a common interface, allowing for the implementation of different methods that are called through the same interface.


### What is a prototype in JavaScript?

- [x] An object from which other objects inherit properties and methods
- [ ] A function that returns a new object
- [ ] A method that belongs to the class itself rather than an instance
- [ ] A reserved word in JavaScript that has a specific meaning

> **Explanation:** A prototype is an object from which other objects inherit properties and methods, forming the basis of JavaScript's inheritance model.


### What is the role of a constructor in a class?

- [x] To initialize object properties when an object is instantiated
- [ ] To define how a property is accessed and modified
- [x] To be called when an object is instantiated
- [ ] To create a class that is a child of another class

> **Explanation:** A constructor is a special method in a class that is called when an object is instantiated, used to initialize object properties.


### What is the significance of the `this` keyword in JavaScript?

- [x] It refers to the object from which a function was called
- [ ] It is used to create an instance of a class
- [ ] It is a function that returns a new object
- [ ] It is used to call functions on an object's parent class

> **Explanation:** The `this` keyword refers to the object from which a function was called and is dynamically scoped based on how a function is invoked.


### What is the difference between a method and a function in JavaScript?

- [x] A method is a function that is a property of an object
- [ ] A method is a function that returns a new object
- [ ] A method is a function that belongs to the class itself rather than an instance
- [ ] A method is a function that is used to call functions on an object's parent class

> **Explanation:** A method is a function that is a property of an object, defining the behavior of objects and can access and modify the object's properties.


### True or False: JavaScript supports both prototypal and class-based inheritance.

- [x] True
- [ ] False

> **Explanation:** JavaScript supports both prototypal and class-based inheritance, allowing for flexible inheritance models.

{{< /quizdown >}}

Remember, this glossary is just the beginning of your journey into the world of Object-Oriented Programming in JavaScript. Keep exploring, stay curious, and enjoy the process of learning and applying these concepts in your projects!

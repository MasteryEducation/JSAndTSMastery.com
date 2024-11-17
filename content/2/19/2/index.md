---
canonical: "https://jsandtsmastery.com/2/19/2"
title: "Metadata Reflection API: Understanding and Using Reflect Metadata in TypeScript"
description: "Explore the Reflect Metadata API in TypeScript to add metadata to classes and methods. Learn how to use, retrieve, and apply metadata in your projects."
linkTitle: "19.2 Metadata Reflection API"
categories:
- TypeScript
- Programming
- Web Development
tags:
- TypeScript
- Reflect Metadata
- Decorators
- Metadata
- Programming
date: 2024-10-25
type: docs
nav_weight: 19200
license: "© 2024 Tokenizer Inc. CC BY-NC-SA 4.0"
---

## 19.2 Metadata Reflection API

In this section, we will delve into the fascinating world of the Metadata Reflection API in TypeScript. This API allows developers to add metadata to classes and methods, which can be incredibly useful for a variety of applications, including frameworks and libraries. We'll explore what the Reflect Metadata API is, how to use it to decorate classes and methods, and how to retrieve and utilize the stored metadata at runtime. We'll also discuss some practical use cases and provide a word of caution regarding its experimental status.

### What is the Reflect Metadata API?

The Reflect Metadata API is a powerful feature in TypeScript that allows developers to define and retrieve metadata for classes and methods. Metadata, in this context, refers to additional information about a program's structure that can be used to enhance or modify its behavior. This API is particularly useful in scenarios where you need to add annotations or extra information to your code, which can then be accessed at runtime.

The Reflect Metadata API is part of the larger Reflect API, which provides a set of methods for intercepting JavaScript operations. It's important to note that the Reflect Metadata API is still experimental, meaning it could change in future releases of TypeScript. Therefore, it's essential to use it with caution and be prepared for potential updates.

### Setting Up Reflect Metadata

Before we dive into examples, let's set up our environment to use the Reflect Metadata API. You'll need to install the `reflect-metadata` package, which provides the necessary functionality.

```bash
npm install reflect-metadata --save
```

Once installed, you should import it at the top of your TypeScript files where you plan to use metadata:

```typescript
import 'reflect-metadata';
```

### Decorating Classes and Methods

Decorators in TypeScript are a special kind of declaration that can be attached to classes, methods, properties, or parameters. They allow you to modify the behavior of the decorated item. With the Reflect Metadata API, you can use decorators to attach metadata to these elements.

#### Example: Adding Metadata to a Class

Let's start by adding metadata to a class. We'll create a simple class and use a decorator to attach metadata to it.

```typescript
import 'reflect-metadata';

function Entity(entityName: string) {
  return function (constructor: Function) {
    Reflect.defineMetadata('entityName', entityName, constructor);
  };
}

@Entity('User')
class User {
  constructor(public name: string, public age: number) {}
}

// Retrieving metadata
const entityName = Reflect.getMetadata('entityName', User);
console.log(`Entity Name: ${entityName}`); // Output: Entity Name: User
```

In this example, we define a decorator `Entity` that takes an `entityName` as an argument. We then use `Reflect.defineMetadata` to attach this metadata to the `User` class. Finally, we retrieve the metadata using `Reflect.getMetadata`.

#### Example: Adding Metadata to a Method

We can also add metadata to methods within a class. Let's see how this works with a simple example.

```typescript
import 'reflect-metadata';

function Log(target: Object, propertyKey: string, descriptor: PropertyDescriptor) {
  Reflect.defineMetadata('log', true, target, propertyKey);
}

class Calculator {
  @Log
  add(a: number, b: number): number {
    return a + b;
  }
}

// Retrieving metadata
const logMetadata = Reflect.getMetadata('log', Calculator.prototype, 'add');
console.log(`Log Metadata: ${logMetadata}`); // Output: Log Metadata: true
```

Here, we define a `Log` decorator that attaches a boolean metadata to the `add` method of the `Calculator` class. We use `Reflect.getMetadata` to retrieve this metadata.

### Retrieving and Using Metadata

Once you've attached metadata to your classes or methods, you can retrieve and use it to influence the behavior of your application. This can be particularly useful in frameworks and libraries where you need to add annotations or configuration options.

#### Example: Conditional Logging

Let's extend our previous example to conditionally log method calls based on metadata.

```typescript
import 'reflect-metadata';

function Log(target: Object, propertyKey: string, descriptor: PropertyDescriptor) {
  Reflect.defineMetadata('log', true, target, propertyKey);

  const originalMethod = descriptor.value;
  descriptor.value = function (...args: any[]) {
    const logMetadata = Reflect.getMetadata('log', target, propertyKey);
    if (logMetadata) {
      console.log(`Calling ${propertyKey} with arguments:`, args);
    }
    return originalMethod.apply(this, args);
  };
}

class Calculator {
  @Log
  add(a: number, b: number): number {
    return a + b;
  }
}

const calculator = new Calculator();
calculator.add(2, 3); // Output: Calling add with arguments: [2, 3]
```

In this example, we modify the `Log` decorator to wrap the original method and check for the `log` metadata. If the metadata is present, we log the method call and its arguments.

### Use Cases in Frameworks and Libraries

The Reflect Metadata API is widely used in frameworks and libraries to add annotations and configuration options. Here are a few examples:

- **Dependency Injection**: Frameworks like Angular use metadata to define dependencies and inject them into classes automatically.
- **ORMs**: Object-Relational Mapping (ORM) libraries use metadata to map classes to database tables and properties to columns.
- **Validation**: Libraries can use metadata to define validation rules for class properties and enforce them at runtime.

### Caution: Experimental Status

As mentioned earlier, the Reflect Metadata API is still experimental. This means that its implementation and behavior might change in future releases of TypeScript. While it's a powerful tool, it's essential to use it with caution and keep an eye on updates from the TypeScript team.

### Try It Yourself

Now that you've learned about the Reflect Metadata API, try experimenting with it in your own projects. Here are a few ideas to get you started:

- Create a decorator that adds metadata to class properties and use it to enforce validation rules.
- Build a simple dependency injection system using metadata to define dependencies.
- Experiment with different types of metadata and see how they can influence your application's behavior.

### Conclusion

The Reflect Metadata API is a powerful feature in TypeScript that allows you to add and retrieve metadata for classes and methods. While it's still experimental, it has many practical applications in frameworks and libraries. By understanding how to use this API, you can enhance your TypeScript applications with additional information and behavior.

## Quiz Time!

{{< quizdown >}}

### What is the Reflect Metadata API used for in TypeScript?

- [x] Adding and retrieving metadata for classes and methods
- [ ] Compiling TypeScript code into JavaScript
- [ ] Managing package dependencies
- [ ] Handling asynchronous operations

> **Explanation:** The Reflect Metadata API is used for adding and retrieving metadata for classes and methods in TypeScript.

### How do you install the `reflect-metadata` package?

- [x] npm install reflect-metadata --save
- [ ] npm install metadata-reflect --save
- [ ] npm install reflect --save
- [ ] npm install metadata --save

> **Explanation:** The correct command to install the `reflect-metadata` package is `npm install reflect-metadata --save`.

### What is a decorator in TypeScript?

- [x] A special kind of declaration that can be attached to classes, methods, properties, or parameters
- [ ] A function that compiles TypeScript code
- [ ] A tool for managing dependencies
- [ ] A method for handling errors

> **Explanation:** A decorator is a special kind of declaration that can be attached to classes, methods, properties, or parameters in TypeScript.

### How do you retrieve metadata from a class using the Reflect Metadata API?

- [x] Reflect.getMetadata('key', target)
- [ ] Reflect.retrieveMetadata('key', target)
- [ ] Reflect.fetchMetadata('key', target)
- [ ] Reflect.obtainMetadata('key', target)

> **Explanation:** You retrieve metadata from a class using the `Reflect.getMetadata('key', target)` method.

### What is the status of the Reflect Metadata API in TypeScript?

- [x] Experimental
- [ ] Stable
- [ ] Deprecated
- [ ] Obsolete

> **Explanation:** The Reflect Metadata API is currently experimental in TypeScript.

### Which of the following is a use case for the Reflect Metadata API?

- [x] Dependency Injection
- [ ] File System Operations
- [ ] Network Requests
- [ ] Error Handling

> **Explanation:** The Reflect Metadata API is used in scenarios like Dependency Injection.

### What should you do before using the Reflect Metadata API in your project?

- [x] Import 'reflect-metadata' at the top of your TypeScript files
- [ ] Install a special TypeScript compiler
- [ ] Configure a new package manager
- [ ] Set up a virtual environment

> **Explanation:** Before using the Reflect Metadata API, you should import 'reflect-metadata' at the top of your TypeScript files.

### What is a potential risk of using the Reflect Metadata API?

- [x] It may change in future releases of TypeScript
- [ ] It causes syntax errors in JavaScript
- [ ] It is incompatible with all TypeScript versions
- [ ] It requires a specific operating system

> **Explanation:** Since the Reflect Metadata API is experimental, it may change in future releases of TypeScript.

### How can metadata influence the behavior of an application?

- [x] By providing additional information that can be used at runtime
- [ ] By compiling code faster
- [ ] By reducing memory usage
- [ ] By improving network speed

> **Explanation:** Metadata provides additional information that can be used at runtime to influence the behavior of an application.

### True or False: The Reflect Metadata API is part of the larger Reflect API.

- [x] True
- [ ] False

> **Explanation:** True. The Reflect Metadata API is indeed part of the larger Reflect API.

{{< /quizdown >}}

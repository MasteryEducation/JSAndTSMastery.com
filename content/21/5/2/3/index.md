---
canonical: "https://jsandtsmastery.com/21/5/2/3"
title: "Chain of Responsibility Pattern in TypeScript: Implementation Guide"
description: "Explore the implementation of the Chain of Responsibility pattern using TypeScript's type system for enhanced reliability and error checking."
linkTitle: "5.2.3 Implementation in TypeScript"
categories:
- Design Patterns
- TypeScript
- Software Development
tags:
- Chain of Responsibility
- TypeScript
- Design Patterns
- Software Architecture
- Error Handling
date: 2024-11-17
type: docs
nav_weight: 5230
license: "© 2024 Tokenizer Inc. CC BY-NC-SA 4.0"
---

## 5.2.3 Implementation in TypeScript

In this section, we will delve into the implementation of the Chain of Responsibility pattern using TypeScript. This pattern is particularly useful for scenarios where multiple handlers can process a request, and the request is passed along a chain until a suitable handler is found. TypeScript's static typing provides an added layer of reliability, ensuring that handlers conform to expected interfaces and catching errors at compile time.

### Understanding the Chain of Responsibility Pattern

The Chain of Responsibility pattern allows an object to send a command without knowing which object will handle it. This is achieved by passing the command along a chain of potential handlers until one of them handles the command. This pattern promotes loose coupling and enhances flexibility in assigning responsibilities to objects.

### Key Components

1. **Handler Interface**: Defines an interface for handling requests and setting the next handler in the chain.
2. **Concrete Handlers**: Implement the handler interface and handle requests they are responsible for.
3. **Client**: Initiates the request to the chain of handlers.

### Implementing the Chain of Responsibility in TypeScript

#### Step 1: Define the Handler Interface

We start by defining an interface for our handlers. This interface will include a method for handling requests and a method for setting the next handler in the chain.

```typescript
interface Handler {
    setNext(handler: Handler): Handler;
    handle(request: string): void;
}
```

- **`setNext(handler: Handler): Handler`**: This method sets the next handler in the chain and returns the handler to allow chaining.
- **`handle(request: string): void`**: This method processes the request. If the handler cannot process it, it passes the request to the next handler.

#### Step 2: Create Concrete Handlers

Next, we implement concrete handlers that will process specific types of requests. Each handler will decide whether to handle the request or pass it to the next handler.

```typescript
class ConcreteHandlerA implements Handler {
    private nextHandler: Handler | null = null;

    public setNext(handler: Handler): Handler {
        this.nextHandler = handler;
        return handler;
    }

    public handle(request: string): void {
        if (request === 'A') {
            console.log('ConcreteHandlerA handled the request.');
        } else if (this.nextHandler) {
            this.nextHandler.handle(request);
        }
    }
}

class ConcreteHandlerB implements Handler {
    private nextHandler: Handler | null = null;

    public setNext(handler: Handler): Handler {
        this.nextHandler = handler;
        return handler;
    }

    public handle(request: string): void {
        if (request === 'B') {
            console.log('ConcreteHandlerB handled the request.');
        } else if (this.nextHandler) {
            this.nextHandler.handle(request);
        }
    }
}
```

- **ConcreteHandlerA and ConcreteHandlerB**: These classes implement the `Handler` interface. They check if they can handle the request; if not, they pass it to the next handler.

#### Step 3: Set Up the Chain

Now, we set up the chain of handlers. The client will initiate the request, and it will be passed along the chain until a handler processes it.

```typescript
const handlerA = new ConcreteHandlerA();
const handlerB = new ConcreteHandlerB();

handlerA.setNext(handlerB);

// Client code
const request = 'B';
handlerA.handle(request);
```

- **Chain Setup**: We create instances of our handlers and link them using the `setNext` method.
- **Client Code**: The client sends a request to the first handler in the chain.

### Benefits of Using TypeScript

1. **Static Typing**: TypeScript's static typing ensures that handlers conform to the expected interface, reducing runtime errors.
2. **Compile-Time Error Checking**: TypeScript catches errors at compile time, making the code more robust and reliable.
3. **Optional Parameters and Default Handling**: TypeScript allows us to define optional parameters and default values, making our handlers more flexible.

#### Implementing Optional Parameters and Default Handling

In some cases, a handler might need to handle requests differently based on additional parameters. TypeScript allows us to define optional parameters and default values to handle such scenarios.

```typescript
class ConcreteHandlerC implements Handler {
    private nextHandler: Handler | null = null;

    public setNext(handler: Handler): Handler {
        this.nextHandler = handler;
        return handler;
    }

    public handle(request: string, context?: any): void {
        if (request === 'C' && context?.priority === 'high') {
            console.log('ConcreteHandlerC handled the high-priority request.');
        } else if (this.nextHandler) {
            this.nextHandler.handle(request, context);
        }
    }
}
```

- **Optional Parameters**: The `handle` method includes an optional `context` parameter, allowing handlers to make decisions based on additional information.
- **Default Handling**: If no handler processes the request, it can be passed to a default handler or logged for further analysis.

### Visualizing the Chain of Responsibility

To better understand how the Chain of Responsibility pattern works, let's visualize the flow of a request through the chain of handlers.

```mermaid
graph LR
    A[Client] --> B[ConcreteHandlerA]
    B -->|Passes request| C[ConcreteHandlerB]
    C -->|Passes request| D[ConcreteHandlerC]
    D -->|Handles request| E[End]
```

- **Diagram Explanation**: The client sends a request to `ConcreteHandlerA`. If `ConcreteHandlerA` cannot handle it, the request is passed to `ConcreteHandlerB`, and so on, until a handler processes the request or it reaches the end of the chain.

### Try It Yourself

Now that we've covered the basics, try modifying the code to add more handlers or change the conditions under which each handler processes requests. Experiment with different request types and see how the chain adapts.

### References and Further Reading

- [MDN Web Docs: Design Patterns](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Design_Patterns)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
- [Refactoring Guru: Chain of Responsibility](https://refactoring.guru/design-patterns/chain-of-responsibility)

### Knowledge Check

Before we wrap up, let's reinforce what we've learned with a few questions and exercises.

1. Define a new handler that processes requests of type 'D' and add it to the chain.
2. Modify the `ConcreteHandlerC` to handle requests based on a different context parameter.
3. What are the advantages of using TypeScript for implementing the Chain of Responsibility pattern?

### Embrace the Journey

Remember, mastering design patterns takes practice and experimentation. As you continue to explore and implement different patterns, you'll gain a deeper understanding of how to structure your code for maintainability and scalability. Keep experimenting, stay curious, and enjoy the journey!

## Quiz Time!

{{< quizdown >}}

### What is the primary purpose of the Chain of Responsibility pattern?

- [x] To pass a request along a chain of handlers until one handles it
- [ ] To ensure only one handler processes a request
- [ ] To prioritize requests based on their type
- [ ] To handle requests in parallel

> **Explanation:** The Chain of Responsibility pattern allows a request to be passed along a chain of handlers until one of them processes it.

### How does TypeScript enhance the implementation of the Chain of Responsibility pattern?

- [x] By providing static typing and compile-time error checking
- [ ] By allowing dynamic typing and runtime error checking
- [ ] By enforcing a strict order of handler execution
- [ ] By optimizing the performance of the chain

> **Explanation:** TypeScript provides static typing and compile-time error checking, ensuring handlers conform to expected interfaces and reducing runtime errors.

### What method is used to set the next handler in the chain?

- [x] `setNext(handler: Handler): Handler`
- [ ] `addHandler(handler: Handler): void`
- [ ] `nextHandler(handler: Handler): Handler`
- [ ] `chainHandler(handler: Handler): void`

> **Explanation:** The `setNext` method is used to set the next handler in the chain and returns the handler to allow chaining.

### In the provided example, which handler processes a request of type 'B'?

- [ ] ConcreteHandlerA
- [x] ConcreteHandlerB
- [ ] ConcreteHandlerC
- [ ] None of the above

> **Explanation:** `ConcreteHandlerB` is responsible for processing requests of type 'B'.

### What is the benefit of using optional parameters in handler methods?

- [x] They allow handlers to make decisions based on additional information
- [ ] They ensure all requests are processed
- [ ] They improve the performance of the chain
- [ ] They enforce strict typing

> **Explanation:** Optional parameters allow handlers to make decisions based on additional information, providing greater flexibility in handling requests.

### How can you visualize the flow of a request through the chain of handlers?

- [x] Using a flowchart or sequence diagram
- [ ] By writing detailed comments in the code
- [ ] By creating a list of handlers
- [ ] By logging each step to the console

> **Explanation:** A flowchart or sequence diagram can visually represent the flow of a request through the chain of handlers.

### What happens if no handler in the chain processes a request?

- [ ] The request is discarded
- [ ] The request is returned to the client
- [x] It can be passed to a default handler or logged
- [ ] The chain restarts from the beginning

> **Explanation:** If no handler processes the request, it can be passed to a default handler or logged for further analysis.

### What is a key advantage of using the Chain of Responsibility pattern?

- [x] It promotes loose coupling and enhances flexibility
- [ ] It ensures all requests are processed
- [ ] It simplifies the client code
- [ ] It guarantees a single handler processes each request

> **Explanation:** The Chain of Responsibility pattern promotes loose coupling and enhances flexibility by allowing requests to be passed along a chain of handlers.

### True or False: TypeScript allows handlers to be dynamically added to the chain at runtime.

- [x] True
- [ ] False

> **Explanation:** TypeScript supports dynamic addition of handlers to the chain at runtime, providing flexibility in modifying the chain.

### Which of the following is NOT a component of the Chain of Responsibility pattern?

- [ ] Handler Interface
- [ ] Concrete Handlers
- [ ] Client
- [x] Singleton

> **Explanation:** The Singleton is not a component of the Chain of Responsibility pattern. The pattern consists of a handler interface, concrete handlers, and a client.

{{< /quizdown >}}

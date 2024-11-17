---
canonical: "https://jsandtsmastery.com/2/7/11"
title: "Utility Types in TypeScript: Simplifying Type Transformations"
description: "Explore TypeScript's built-in utility types like Partial, Required, Readonly, and more. Learn how these utility types simplify complex type transformations with practical examples."
linkTitle: "7.11 Utility Types"
categories:
- TypeScript
- Programming
- Web Development
tags:
- TypeScript
- Utility Types
- Partial
- Required
- Readonly
date: 2024-10-25
type: docs
nav_weight: 8100
license: "© 2024 Tokenizer Inc. CC BY-NC-SA 4.0"
---

## 7.11 Utility Types

Welcome to the fascinating world of TypeScript utility types! As you continue your journey in learning TypeScript, you'll discover that utility types are powerful tools that can significantly simplify your code. They allow you to transform existing types in various ways, making your code more flexible and easier to maintain. In this section, we'll explore some of the most commonly used utility types provided by TypeScript, including `Partial`, `Required`, `Readonly`, and more. We'll explain their purpose, demonstrate their usage with examples, and show you how they can simplify complex type transformations.

### What Are Utility Types?

Utility types are predefined types in TypeScript that provide type transformations. They allow you to create new types based on existing ones, enabling you to modify the properties of a type without having to redefine the entire type. This can be incredibly useful when working with complex data structures or when you want to enforce certain constraints on your types.

### Common Utility Types

Let's dive into some of the most commonly used utility types in TypeScript:

#### 1. `Partial<T>`

The `Partial` utility type is used to make all properties of a type optional. This is particularly useful when you want to work with objects that may not have all properties defined.

```typescript
interface User {
  name: string;
  age: number;
  email: string;
}

// Create a partial user where all properties are optional
const updateUser: Partial<User> = {
  email: "newemail@example.com"
};
```

In this example, `updateUser` can have any combination of `name`, `age`, and `email`, or none at all.

#### 2. `Required<T>`

The `Required` utility type is the opposite of `Partial`. It makes all properties of a type required. This is useful when you want to ensure that all properties are provided.

```typescript
interface User {
  name?: string;
  age?: number;
  email?: string;
}

// Make all properties required
const completeUser: Required<User> = {
  name: "Alice",
  age: 30,
  email: "alice@example.com"
};
```

Here, `completeUser` must include `name`, `age`, and `email`.

#### 3. `Readonly<T>`

The `Readonly` utility type makes all properties of a type immutable. Once a property is set, it cannot be changed.

```typescript
interface User {
  name: string;
  age: number;
  email: string;
}

// Create a readonly user
const readonlyUser: Readonly<User> = {
  name: "Bob",
  age: 25,
  email: "bob@example.com"
};

// Error: Cannot assign to 'name' because it is a read-only property
// readonlyUser.name = "Charlie";
```

In this example, trying to change any property of `readonlyUser` will result in a compile-time error.

#### 4. `Pick<T, K>`

The `Pick` utility type allows you to create a new type by selecting a subset of properties from an existing type.

```typescript
interface User {
  name: string;
  age: number;
  email: string;
}

// Pick only 'name' and 'email' properties
type UserContactInfo = Pick<User, "name" | "email">;

const contactInfo: UserContactInfo = {
  name: "Dave",
  email: "dave@example.com"
};
```

Here, `UserContactInfo` only includes the `name` and `email` properties from `User`.

#### 5. `Omit<T, K>`

The `Omit` utility type is the opposite of `Pick`. It allows you to create a new type by excluding certain properties from an existing type.

```typescript
interface User {
  name: string;
  age: number;
  email: string;
}

// Omit 'email' property
type UserWithoutEmail = Omit<User, "email">;

const userWithoutEmail: UserWithoutEmail = {
  name: "Eve",
  age: 28
};
```

In this example, `UserWithoutEmail` excludes the `email` property from `User`.

#### 6. `Record<K, T>`

The `Record` utility type is used to create a type with a set of properties `K` of type `T`. This is useful when you want to create a map-like structure.

```typescript
type Role = "admin" | "user" | "guest";

// Create a record type where each role has a boolean value
const rolePermissions: Record<Role, boolean> = {
  admin: true,
  user: false,
  guest: false
};
```

Here, `rolePermissions` is a map where each role is associated with a boolean value.

#### 7. `Exclude<T, U>`

The `Exclude` utility type is used to create a new type by excluding certain types from a union.

```typescript
type AllRoles = "admin" | "user" | "guest";

// Exclude 'guest' role
type NonGuestRoles = Exclude<AllRoles, "guest">;

const role: NonGuestRoles = "admin"; // Valid
// const guestRole: NonGuestRoles = "guest"; // Error
```

In this example, `NonGuestRoles` excludes the `guest` role from `AllRoles`.

#### 8. `Extract<T, U>`

The `Extract` utility type is the opposite of `Exclude`. It creates a new type by extracting certain types from a union.

```typescript
type AllRoles = "admin" | "user" | "guest";

// Extract 'admin' and 'user' roles
type AdminOrUser = Extract<AllRoles, "admin" | "user">;

const role: AdminOrUser = "user"; // Valid
// const guestRole: AdminOrUser = "guest"; // Error
```

Here, `AdminOrUser` includes only the `admin` and `user` roles from `AllRoles`.

#### 9. `NonNullable<T>`

The `NonNullable` utility type removes `null` and `undefined` from a type.

```typescript
type MaybeString = string | null | undefined;

// Remove null and undefined
type DefiniteString = NonNullable<MaybeString>;

const str: DefiniteString = "Hello"; // Valid
// const nullStr: DefiniteString = null; // Error
```

In this example, `DefiniteString` excludes `null` and `undefined` from `MaybeString`.

#### 10. `ReturnType<T>`

The `ReturnType` utility type extracts the return type of a function.

```typescript
function getUser() {
  return { name: "Frank", age: 40 };
}

// Extract return type of getUser
type UserType = ReturnType<typeof getUser>;

const user: UserType = { name: "Frank", age: 40 };
```

Here, `UserType` is the return type of the `getUser` function.

### Simplifying Complex Type Transformations

Utility types are incredibly useful for simplifying complex type transformations. They allow you to modify existing types without having to redefine them, making your code more maintainable and flexible. Let's look at a practical example:

#### Example: Configurable User Settings

Imagine you have a user settings object with various properties, and you want to create a type that represents a partial update to these settings. You can use the `Partial` utility type to achieve this:

```typescript
interface UserSettings {
  theme: string;
  notifications: boolean;
  privacyMode: boolean;
}

// Create a type for partial updates
type PartialUserSettings = Partial<UserSettings>;

const updateSettings: PartialUserSettings = {
  theme: "dark"
};
```

In this example, `PartialUserSettings` allows you to update only the properties you need, without requiring all properties to be specified.

### Combining Utility Types

You can also combine utility types to solve more complex problems. Let's say you want to create a type that represents a readonly version of a user's contact information, but only includes the `name` and `email` properties. You can achieve this by combining `Pick` and `Readonly`:

```typescript
interface User {
  name: string;
  age: number;
  email: string;
}

// Combine Pick and Readonly
type ReadonlyContactInfo = Readonly<Pick<User, "name" | "email">>;

const contactInfo: ReadonlyContactInfo = {
  name: "Grace",
  email: "grace@example.com"
};

// Error: Cannot assign to 'name' because it is a read-only property
// contactInfo.name = "Hannah";
```

Here, `ReadonlyContactInfo` is a readonly type that only includes the `name` and `email` properties from `User`.

### Exploring Utility Types Further

While we've covered some of the most commonly used utility types, TypeScript offers many more. To explore them further, we encourage you to visit the [TypeScript Utility Types documentation](https://www.typescriptlang.org/docs/handbook/utility-types.html). There, you'll find additional utility types like `InstanceType`, `ThisType`, and more.

### Try It Yourself

To reinforce your understanding of utility types, try modifying the examples above. For instance, create a new type that combines `Omit` and `Readonly` to exclude certain properties and make the remaining ones readonly. Experiment with different combinations to see how utility types can simplify your code.

### Summary

In this section, we've explored the power of TypeScript utility types. These built-in types allow you to transform existing types in various ways, making your code more flexible and easier to maintain. By using utility types like `Partial`, `Required`, `Readonly`, and others, you can simplify complex type transformations and enforce constraints on your types. As you continue your journey with TypeScript, keep these utility types in mind and explore how they can help you write cleaner, more maintainable code.

## Quiz Time!

{{< quizdown >}}

### Which utility type makes all properties of a type optional?

- [x] Partial
- [ ] Required
- [ ] Readonly
- [ ] Pick

> **Explanation:** The `Partial` utility type makes all properties of a type optional.

### What does the `Required` utility type do?

- [ ] Makes all properties optional
- [x] Makes all properties required
- [ ] Makes all properties readonly
- [ ] Excludes certain properties

> **Explanation:** The `Required` utility type makes all properties of a type required.

### How does the `Readonly` utility type affect a type?

- [ ] Makes all properties optional
- [ ] Makes all properties required
- [x] Makes all properties immutable
- [ ] Excludes certain properties

> **Explanation:** The `Readonly` utility type makes all properties of a type immutable.

### Which utility type allows you to select a subset of properties from a type?

- [ ] Omit
- [ ] Required
- [x] Pick
- [ ] Partial

> **Explanation:** The `Pick` utility type allows you to select a subset of properties from a type.

### What does the `Omit` utility type do?

- [ ] Includes certain properties
- [x] Excludes certain properties
- [ ] Makes all properties required
- [ ] Makes all properties optional

> **Explanation:** The `Omit` utility type creates a new type by excluding certain properties from an existing type.

### Which utility type creates a map-like structure with a set of properties?

- [ ] Pick
- [ ] Omit
- [ ] Partial
- [x] Record

> **Explanation:** The `Record` utility type is used to create a type with a set of properties of a specified type.

### How does the `Exclude` utility type work?

- [ ] Includes certain types
- [x] Excludes certain types from a union
- [ ] Makes all properties required
- [ ] Makes all properties optional

> **Explanation:** The `Exclude` utility type creates a new type by excluding certain types from a union.

### What is the purpose of the `Extract` utility type?

- [ ] Excludes certain types
- [x] Extracts certain types from a union
- [ ] Makes all properties required
- [ ] Makes all properties optional

> **Explanation:** The `Extract` utility type creates a new type by extracting certain types from a union.

### Which utility type removes `null` and `undefined` from a type?

- [ ] Partial
- [ ] Required
- [ ] Pick
- [x] NonNullable

> **Explanation:** The `NonNullable` utility type removes `null` and `undefined` from a type.

### True or False: The `ReturnType` utility type extracts the return type of a function.

- [x] True
- [ ] False

> **Explanation:** The `ReturnType` utility type is used to extract the return type of a function.

{{< /quizdown >}}

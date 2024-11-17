---
canonical: "https://jsandtsmastery.com/1/2/5"
title: "Saving and Running JavaScript Files: A Beginner's Guide"
description: "Learn how to save and run JavaScript files, understand inline and external scripts, and organize your project files effectively."
linkTitle: "2.5 Saving and Running JavaScript Files"
categories:
- JavaScript
- Programming
- Web Development
tags:
- JavaScript
- HTML
- Web Development
- Coding
- Beginner Guide
date: 2024-10-25
type: docs
nav_weight: 2500
license: "© 2024 Tokenizer Inc. CC BY-NC-SA 4.0"
---

## 2.5 Saving and Running JavaScript Files

In this section, we'll explore how to save and run JavaScript files, understand the difference between inline JavaScript and external `.js` files, and learn best practices for organizing your project files. By the end of this guide, you'll be equipped to write, save, and execute your JavaScript code efficiently.

### Understanding Inline JavaScript vs. External JavaScript Files

JavaScript can be included in HTML documents in two primary ways: inline and external files. Each method has its advantages and use cases. Let's delve into each one to understand their differences and when to use them.

#### Inline JavaScript

Inline JavaScript is written directly within an HTML document. This method involves embedding JavaScript code inside the `<script>` tag within the HTML file. Here's a simple example:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Inline JavaScript Example</title>
</head>
<body>
    <h1>Hello, World!</h1>
    <script>
        // This is an inline JavaScript example
        console.log('Hello from inline JavaScript!');
    </script>
</body>
</html>
```

**Advantages of Inline JavaScript:**

- **Simplicity:** Easy to use for small scripts or quick testing.
- **Immediate Access:** The script is readily accessible within the HTML file, making it convenient for small projects.

**Disadvantages of Inline JavaScript:**

- **Maintainability:** Becomes difficult to manage as the codebase grows.
- **Reusability:** Code cannot be reused across multiple HTML files without duplication.
- **Performance:** Can slow down page load times if used excessively.

#### External JavaScript Files

External JavaScript involves writing JavaScript code in a separate file with a `.js` extension and linking it to the HTML document. This method is preferred for larger projects. Here's how you can create and link an external JavaScript file:

1. **Create a JavaScript File:** Save your JavaScript code in a file with a `.js` extension, for example, `script.js`.

```javascript
// script.js
console.log('Hello from external JavaScript!');
```

2. **Link the JavaScript File to HTML:** Use the `<script src="">` tag to link the external JavaScript file to your HTML document.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>External JavaScript Example</title>
</head>
<body>
    <h1>Hello, World!</h1>
    <script src="script.js"></script>
</body>
</html>
```

**Advantages of External JavaScript:**

- **Maintainability:** Easier to manage and organize code, especially in larger projects.
- **Reusability:** Code can be reused across multiple HTML files.
- **Performance:** Improves page load times by allowing browsers to cache the JavaScript file.

**Disadvantages of External JavaScript:**

- **Initial Setup:** Requires additional steps to create and link the file.
- **Dependency:** The HTML file depends on the external file being correctly linked and available.

### Linking JavaScript Files to HTML

Linking JavaScript files to HTML is a straightforward process, but it's important to follow best practices to ensure your scripts run smoothly.

#### Using the `<script src="">` Tag

The `<script>` tag is used to embed or reference JavaScript code in an HTML document. When linking an external JavaScript file, the `src` attribute specifies the path to the `.js` file.

- **Relative Path:** Use a relative path if the JavaScript file is located in the same directory or a subdirectory of the HTML file.

```html
<script src="script.js"></script>
```

- **Absolute Path:** Use an absolute path if the JavaScript file is hosted on a different server or domain.

```html
<script src="https://example.com/script.js"></script>
```

#### Placement of the `<script>` Tag

The placement of the `<script>` tag in your HTML document can affect how your page loads and performs. Here are some common practices:

- **Head Section:** Placing the `<script>` tag in the `<head>` section can block the rendering of the page until the script is downloaded and executed. This is generally not recommended unless the script is necessary for the initial rendering of the page.

```html
<head>
    <script src="script.js"></script>
</head>
```

- **End of the Body:** Placing the `<script>` tag just before the closing `</body>` tag is a common practice. This ensures that the HTML content is loaded before the JavaScript is executed, improving page load times.

```html
<body>
    <!-- HTML content -->
    <script src="script.js"></script>
</body>
```

- **Asynchronous and Deferred Loading:** Use the `async` or `defer` attributes to control the loading and execution of scripts.

  - **Async:** The script is executed as soon as it is downloaded, without blocking the HTML parsing.

  ```html
  <script src="script.js" async></script>
  ```

  - **Defer:** The script is executed after the HTML document has been fully parsed.

  ```html
  <script src="script.js" defer></script>
  ```

### Best Practices for Organizing Project Files and Directories

Organizing your project files and directories is crucial for maintaining a clean and efficient workflow. Here are some best practices to consider:

#### 1. Use a Consistent Directory Structure

Organize your files into a logical directory structure. A common structure for web projects includes separate directories for HTML, CSS, JavaScript, and assets (such as images and fonts).

```
project/
│
├── index.html
├── css/
│   └── styles.css
├── js/
│   └── script.js
└── assets/
    └── images/
        └── logo.png
```

#### 2. Use Descriptive File and Directory Names

Choose descriptive names for your files and directories to make it easier to understand their purpose. Avoid using spaces or special characters in file names; instead, use hyphens or underscores.

#### 3. Separate Concerns

Keep HTML, CSS, and JavaScript files separate to adhere to the principle of separation of concerns. This makes your code more modular and easier to maintain.

#### 4. Use Version Control

Consider using version control systems like Git to track changes to your code and collaborate with others. This is especially useful for larger projects or when working in teams.

#### 5. Keep Your Code DRY

Follow the DRY (Don't Repeat Yourself) principle by avoiding code duplication. Reuse code through functions, modules, or libraries to make your codebase more efficient.

### Try It Yourself

Let's put what we've learned into practice. Create a simple HTML file and an external JavaScript file, then link them together.

1. **Create an HTML File:** Save the following code as `index.html`.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Try It Yourself</title>
</head>
<body>
    <h1>Welcome to JavaScript!</h1>
    <p>Check the console for a message.</p>
    <script src="script.js"></script>
</body>
</html>
```

2. **Create a JavaScript File:** Save the following code as `script.js`.

```javascript
// script.js
console.log('Congratulations! You have successfully linked your JavaScript file.');
```

3. **Run Your Code:** Open `index.html` in a web browser and open the developer console (usually accessible via F12 or right-click > Inspect > Console) to see the message.

### Summary

In this section, we've explored the differences between inline and external JavaScript, learned how to link JavaScript files to HTML, and discussed best practices for organizing project files. By following these guidelines, you'll be able to write, save, and run your JavaScript code effectively, setting a strong foundation for your programming journey.

### Further Reading

For more information on JavaScript and HTML, consider exploring the following resources:

- [MDN Web Docs: JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- [W3Schools: JavaScript Tutorial](https://www.w3schools.com/js/)
- [MDN Web Docs: HTML `<script>` Tag](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)

## Quiz Time!

{{< quizdown >}}

### What is the main advantage of using external JavaScript files over inline JavaScript?

- [x] Code reusability across multiple HTML files
- [ ] Easier to write for small scripts
- [ ] Faster execution time
- [ ] Requires fewer files

> **Explanation:** External JavaScript files allow code to be reused across multiple HTML files, making them more maintainable.

### Where is it generally recommended to place the `<script>` tag in an HTML document?

- [ ] In the `<head>` section
- [x] Just before the closing `</body>` tag
- [ ] At the top of the `<body>` section
- [ ] Anywhere in the document

> **Explanation:** Placing the `<script>` tag just before the closing `</body>` tag ensures that the HTML content loads before the script executes, improving page load times.

### Which attribute can be used to defer the execution of a JavaScript file until the HTML document is fully parsed?

- [ ] async
- [x] defer
- [ ] src
- [ ] type

> **Explanation:** The `defer` attribute delays the execution of the script until the HTML document is fully parsed.

### What is a common disadvantage of using inline JavaScript?

- [x] Difficult to maintain as the codebase grows
- [ ] Requires additional setup
- [ ] Cannot be used for small scripts
- [ ] Slower execution time

> **Explanation:** Inline JavaScript can become difficult to maintain as the codebase grows, making it less suitable for larger projects.

### What is the purpose of using a consistent directory structure in a project?

- [x] To organize files logically and improve maintainability
- [ ] To reduce the number of files in a project
- [ ] To increase the execution speed of scripts
- [ ] To make the project look more professional

> **Explanation:** A consistent directory structure helps organize files logically, making the project easier to maintain and navigate.

### Which of the following is a best practice for naming files and directories?

- [x] Use descriptive names without spaces or special characters
- [ ] Use short, cryptic names to save space
- [ ] Include spaces for readability
- [ ] Use special characters to make names unique

> **Explanation:** Descriptive names without spaces or special characters improve readability and avoid issues with file paths.

### What does the DRY principle stand for?

- [x] Don't Repeat Yourself
- [ ] Don't Run Yet
- [ ] Do Repeat Yourself
- [ ] Do Run Yourself

> **Explanation:** The DRY principle stands for "Don't Repeat Yourself," encouraging code reuse to avoid duplication.

### How can you link an external JavaScript file to an HTML document?

- [x] Using the `<script src="path/to/file.js"></script>` tag
- [ ] Embedding the code within the `<head>` section
- [ ] Using the `<link>` tag
- [ ] Including the file in a `<style>` tag

> **Explanation:** The `<script src="path/to/file.js"></script>` tag is used to link an external JavaScript file to an HTML document.

### What is the effect of using the `async` attribute on a `<script>` tag?

- [x] The script is executed as soon as it is downloaded
- [ ] The script is executed after the HTML document is fully parsed
- [ ] The script is ignored by the browser
- [ ] The script is executed before any HTML is parsed

> **Explanation:** The `async` attribute allows the script to be executed as soon as it is downloaded, without blocking HTML parsing.

### True or False: Inline JavaScript is always better than external JavaScript for large projects.

- [ ] True
- [x] False

> **Explanation:** False. External JavaScript is generally better for large projects due to its maintainability and reusability.

{{< /quizdown >}}

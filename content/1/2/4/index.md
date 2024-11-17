---
canonical: "https://jsandtsmastery.com/1/2/4"
title: "JavaScript Basics: Writing Your First Program - 'Hello, World!'"
description: "Learn how to write your first JavaScript program with a step-by-step guide to creating a basic HTML file structure and embedding JavaScript."
linkTitle: "2.4 Writing Your First Program: 'Hello, World!'"
categories:
- JavaScript
- Programming
- Web Development
tags:
- JavaScript
- Hello World
- Beginner Programming
- Web Development
- HTML
date: 2024-10-25
type: docs
nav_weight: 2400
license: "© 2024 Tokenizer Inc. CC BY-NC-SA 4.0"
---

## 2.4 Writing Your First Program: "Hello, World!"

Welcome to the exciting world of programming! In this section, we will guide you through writing your first JavaScript program: the classic "Hello, World!" This is a rite of passage for every programmer, marking the beginning of your journey into coding. By the end of this guide, you will have a solid understanding of how to create a basic HTML file, embed JavaScript, and display output using different methods.

### Understanding the Basics

Before we dive into writing code, let's briefly discuss the components we'll be working with:

- **HTML (HyperText Markup Language):** This is the standard language for creating web pages. It provides the structure of a webpage.
- **JavaScript:** A programming language that allows you to implement complex features on web pages, such as dynamically updating content, controlling multimedia, and much more.
- **Web Browser:** A software application used to access information on the World Wide Web. Browsers can interpret HTML and execute JavaScript.

### Creating a Basic HTML File Structure

To begin, we need to create a simple HTML file that will serve as the foundation for our JavaScript code. Follow these steps:

1. **Open Your Text Editor:** Use any text editor you prefer, such as Visual Studio Code, Sublime Text, or Notepad++.

2. **Create a New File:** Save this file with a `.html` extension, for example, `hello_world.html`.

3. **Write the Basic HTML Structure:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hello, World!</title>
</head>
<body>
    <h1>Welcome to JavaScript Programming!</h1>
</body>
</html>
```

#### Explanation:

- `<!DOCTYPE html>`: Declares the document type and version of HTML.
- `<html lang="en">`: The root element of the HTML document, with a language attribute set to English.
- `<head>`: Contains metadata and links to stylesheets or scripts.
- `<meta charset="UTF-8">`: Sets the character encoding for the document.
- `<meta name="viewport" content="width=device-width, initial-scale=1.0">`: Ensures the webpage is responsive on different devices.
- `<title>`: Sets the title of the webpage, displayed in the browser's title bar.
- `<body>`: Contains the content of the webpage.

### Embedding JavaScript Using `<script>` Tags

Now that we have our HTML structure, let's embed JavaScript into our file. We will use the `<script>` tag, which tells the browser to execute the code within it.

#### Adding JavaScript to Your HTML

1. **Place the `<script>` Tag:**

   You can place the `<script>` tag either in the `<head>` or at the end of the `<body>` section. For this example, we'll place it at the end of the `<body>` to ensure the HTML content loads before the script runs.

```html
<body>
    <h1>Welcome to JavaScript Programming!</h1>

    <script>
        // This is where our JavaScript code will go
    </script>
</body>
```

#### Explanation:

- `<script>`: The tag used to embed JavaScript code within an HTML document.
- Comments (`//`): Used to annotate code, making it easier to understand. Comments are ignored by the browser.

### Displaying Output in JavaScript

JavaScript provides several methods to display output. We'll explore three common methods: `console.log()`, `alert()`, and `document.write()`.

#### Using `console.log()`

The `console.log()` method is used to print messages to the browser's console. It's a great tool for debugging and testing code.

```html
<script>
    // Displaying output in the console
    console.log("Hello, World!");
</script>
```

- **How to View the Console:**
  - Open your web browser.
  - Right-click on the page and select "Inspect" or press `Ctrl + Shift + I` (Windows/Linux) or `Cmd + Option + I` (Mac).
  - Navigate to the "Console" tab to see the output.

#### Using `alert()`

The `alert()` method displays a pop-up dialog box with a message. It's useful for grabbing the user's attention.

```html
<script>
    // Displaying output using an alert box
    alert("Hello, World!");
</script>
```

- **Try It Yourself:** Open your HTML file in a browser to see the alert box in action.

#### Using `document.write()`

The `document.write()` method writes directly to the HTML document. It's often used for testing but not recommended for production code as it can overwrite existing content.

```html
<script>
    // Displaying output directly on the webpage
    document.write("Hello, World!");
</script>
```

- **Note:** Using `document.write()` after the page has loaded can erase the entire page content.

### Complete Example: "Hello, World!"

Let's combine everything we've learned into a complete example. Below is the full HTML file with embedded JavaScript:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hello, World!</title>
</head>
<body>
    <h1>Welcome to JavaScript Programming!</h1>

    <script>
        // Displaying output in the console
        console.log("Hello, World!");

        // Displaying output using an alert box
        alert("Hello, World!");

        // Displaying output directly on the webpage
        document.write("Hello, World!");
    </script>
</body>
</html>
```

### Visualizing the Process

To help you understand the flow of how JavaScript interacts with HTML, let's visualize the process using a simple flowchart.

```mermaid
flowchart TD
    A[Start] --> B[Create HTML File]
    B --> C[Add HTML Structure]
    C --> D[Embed JavaScript with <script>]
    D --> E{Choose Output Method}
    E --> |Console| F[Use console.log()]
    E --> |Alert| G[Use alert()]
    E --> |Document| H[Use document.write()]
    F --> I[View Output in Console]
    G --> J[View Alert Box]
    H --> K[View Output on Webpage]
    I --> L[End]
    J --> L
    K --> L
```

### Try It Yourself

Experiment with the code examples provided. Here are some suggestions:

- **Modify the Message:** Change "Hello, World!" to a message of your choice.
- **Add More Output Methods:** Try using all three methods (`console.log()`, `alert()`, `document.write()`) to display different messages.
- **Combine Methods:** Use multiple methods in one script to see how they interact.

### Additional Resources

For further reading and a deeper dive into JavaScript and HTML, consider exploring the following resources:

- [MDN Web Docs: JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- [W3Schools: JavaScript Tutorial](https://www.w3schools.com/js/)
- [JavaScript.info: The Modern JavaScript Tutorial](https://javascript.info/)

### Key Takeaways

- **HTML provides the structure** for your web pages, while JavaScript adds interactivity.
- **The `<script>` tag** is used to embed JavaScript into HTML.
- **Output methods** like `console.log()`, `alert()`, and `document.write()` help display information.
- **Experimenting with code** is crucial for learning and understanding programming concepts.

## Quiz Time!

{{< quizdown >}}

### What is the purpose of the `<script>` tag in HTML?

- [x] To embed JavaScript code within an HTML document
- [ ] To style HTML elements
- [ ] To add metadata to a webpage
- [ ] To create hyperlinks

> **Explanation:** The `<script>` tag is used to embed or reference JavaScript code within an HTML document, allowing the browser to execute the script.

### Which method is used to display a message in the browser's console?

- [x] console.log()
- [ ] alert()
- [ ] document.write()
- [ ] console.display()

> **Explanation:** The `console.log()` method is used to print messages to the browser's console, which is useful for debugging and testing code.

### What happens if you use `document.write()` after the page has loaded?

- [x] It can overwrite the entire page content
- [ ] It displays an alert box
- [ ] It logs a message to the console
- [ ] It has no effect

> **Explanation:** Using `document.write()` after the page has loaded can erase the entire content of the page, as it writes directly to the document.

### Which method displays a pop-up dialog box with a message?

- [x] alert()
- [ ] console.log()
- [ ] document.write()
- [ ] prompt()

> **Explanation:** The `alert()` method displays a pop-up dialog box with a specified message, which is useful for grabbing the user's attention.

### Where can you place the `<script>` tag in an HTML document?

- [x] In the `<head>` section
- [x] At the end of the `<body>` section
- [ ] Inside the `<title>` tag
- [ ] Inside the `<meta>` tag

> **Explanation:** The `<script>` tag can be placed in the `<head>` section or at the end of the `<body>` section. Placing it at the end of the `<body>` ensures that the HTML content loads before the script runs.

### What is the file extension for HTML files?

- [x] .html
- [ ] .js
- [ ] .css
- [ ] .txt

> **Explanation:** HTML files are saved with a `.html` extension, which indicates that the file contains HTML code.

### What does `<!DOCTYPE html>` declare?

- [x] The document type and version of HTML
- [ ] The language of the document
- [ ] The character encoding
- [ ] The title of the document

> **Explanation:** `<!DOCTYPE html>` declares the document type and version of HTML, helping the browser to render the page correctly.

### Which of the following is NOT a method to display output in JavaScript?

- [ ] console.log()
- [ ] alert()
- [ ] document.write()
- [x] console.alert()

> **Explanation:** `console.alert()` is not a valid method in JavaScript. The correct methods are `console.log()`, `alert()`, and `document.write()`.

### What is the purpose of comments in JavaScript code?

- [x] To annotate code and make it easier to understand
- [ ] To execute code
- [ ] To style HTML elements
- [ ] To create hyperlinks

> **Explanation:** Comments are used to annotate code, providing explanations or notes that make the code easier to understand. They are ignored by the browser.

### True or False: JavaScript can only be used for web development.

- [ ] True
- [x] False

> **Explanation:** False. While JavaScript is primarily used for web development, it is also used in server-side programming, mobile app development, and more.

{{< /quizdown >}}

By following this guide, you've taken your first steps into the world of JavaScript programming. Keep experimenting and exploring to deepen your understanding and skills. Happy coding!

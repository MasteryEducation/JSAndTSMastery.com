---
canonical: "https://jsandtsmastery.com/2/16/5"
title: "Axios for HTTP Requests in TypeScript: Setup, Usage, and Best Practices"
description: "Learn how to set up and use Axios for HTTP requests in TypeScript, including installation, request examples, interceptors, headers, and error handling."
linkTitle: "16.5 Using Axios for HTTP Requests"
categories:
- TypeScript
- HTTP Requests
- Web Development
tags:
- Axios
- TypeScript
- HTTP
- API
- Web Development
date: 2024-10-25
type: docs
nav_weight: 16500
license: "© 2024 Tokenizer Inc. CC BY-NC-SA 4.0"
---

## 16.5 Using Axios for HTTP Requests

In this section, we will explore Axios, a popular library for making HTTP requests, and how it can be used effectively with TypeScript. Axios provides a simple and powerful API for handling HTTP requests, offering advantages over the built-in `fetch` API. Let's dive into setting up Axios, making requests, configuring headers, handling errors, and more.

### Introduction to Axios

**Axios** is a promise-based HTTP client for the browser and Node.js. It simplifies the process of making HTTP requests and provides a more intuitive API compared to the native `fetch` API. Some of the key advantages of using Axios include:

- **Automatic JSON Transformation**: Axios automatically transforms JSON data, making it easier to work with API responses.
- **Request and Response Interceptors**: Axios allows you to intercept requests or responses before they are handled, enabling you to modify them or handle errors globally.
- **Cancellation**: Axios supports request cancellation, which is useful for aborting requests that are no longer needed.
- **Wide Browser Support**: Axios works in older browsers that do not support the `fetch` API.
- **Timeouts**: Axios allows you to set timeouts for requests, providing better control over long-running requests.

### Installing and Setting Up Axios with TypeScript

Before we can use Axios in our TypeScript project, we need to install it. You can install Axios using npm or yarn:

```bash
npm install axios

yarn add axios
```

Additionally, to ensure TypeScript understands the Axios types, you should install the Axios type definitions:

```bash
npm install @types/axios

yarn add @types/axios
```

Once Axios is installed, you can import it into your TypeScript files and start making HTTP requests.

### Making HTTP Requests with Axios

Let's look at how to make basic HTTP requests using Axios. We'll cover GET, POST, PUT, and DELETE requests, which are the most common HTTP methods used when interacting with APIs.

#### GET Request

A GET request is used to retrieve data from a server. Here's how you can make a GET request using Axios:

```typescript
import axios from 'axios';

// Define a function to fetch data from an API
async function fetchData(url: string): Promise<void> {
  try {
    const response = await axios.get(url);
    console.log('Data:', response.data);
  } catch (error) {
    console.error('Error fetching data:', error);
  }
}

// Call the function with a URL
fetchData('https://jsonplaceholder.typicode.com/posts');
```

In this example, we use `axios.get()` to send a GET request to the specified URL. The response is logged to the console, and any errors are caught and logged.

#### POST Request

A POST request is used to send data to a server. Here's an example of making a POST request with Axios:

```typescript
import axios from 'axios';

// Define a function to send data to an API
async function postData(url: string, data: object): Promise<void> {
  try {
    const response = await axios.post(url, data);
    console.log('Response:', response.data);
  } catch (error) {
    console.error('Error posting data:', error);
  }
}

// Call the function with a URL and data
postData('https://jsonplaceholder.typicode.com/posts', {
  title: 'New Post',
  body: 'This is the content of the post.',
  userId: 1
});
```

In this example, `axios.post()` is used to send data to the server. The data is passed as the second argument to the `post()` method.

#### PUT Request

A PUT request is used to update existing data on the server. Here's how you can make a PUT request with Axios:

```typescript
import axios from 'axios';

// Define a function to update data on an API
async function updateData(url: string, data: object): Promise<void> {
  try {
    const response = await axios.put(url, data);
    console.log('Updated Data:', response.data);
  } catch (error) {
    console.error('Error updating data:', error);
  }
}

// Call the function with a URL and data
updateData('https://jsonplaceholder.typicode.com/posts/1', {
  id: 1,
  title: 'Updated Post',
  body: 'This is the updated content of the post.',
  userId: 1
});
```

In this example, `axios.put()` is used to update data on the server. The URL includes the ID of the resource to be updated.

#### DELETE Request

A DELETE request is used to remove data from the server. Here's an example of making a DELETE request with Axios:

```typescript
import axios from 'axios';

// Define a function to delete data from an API
async function deleteData(url: string): Promise<void> {
  try {
    const response = await axios.delete(url);
    console.log('Deleted:', response.data);
  } catch (error) {
    console.error('Error deleting data:', error);
  }
}

// Call the function with a URL
deleteData('https://jsonplaceholder.typicode.com/posts/1');
```

In this example, `axios.delete()` is used to remove data from the server. The URL includes the ID of the resource to be deleted.

### Configuring Axios Requests

Axios provides several options for configuring requests, including setting headers, timeouts, and base URLs.

#### Setting Headers

Headers are often used to send additional information with HTTP requests. Here's how you can set headers using Axios:

```typescript
import axios from 'axios';

// Define a function to fetch data with custom headers
async function fetchDataWithHeaders(url: string): Promise<void> {
  try {
    const response = await axios.get(url, {
      headers: {
        'Authorization': 'Bearer your-token',
        'Content-Type': 'application/json'
      }
    });
    console.log('Data:', response.data);
  } catch (error) {
    console.error('Error fetching data:', error);
  }
}

// Call the function with a URL
fetchDataWithHeaders('https://jsonplaceholder.typicode.com/posts');
```

In this example, we set custom headers using the `headers` option in the request configuration.

#### Setting a Base URL

If you are making multiple requests to the same server, you can set a base URL to avoid repeating the server address:

```typescript
import axios from 'axios';

// Create an Axios instance with a base URL
const apiClient = axios.create({
  baseURL: 'https://jsonplaceholder.typicode.com'
});

// Define a function to fetch data using the Axios instance
async function fetchData(): Promise<void> {
  try {
    const response = await apiClient.get('/posts');
    console.log('Data:', response.data);
  } catch (error) {
    console.error('Error fetching data:', error);
  }
}

// Call the function
fetchData();
```

In this example, we create an Axios instance with a `baseURL` configuration. This allows us to make requests without specifying the full URL each time.

### Using Axios Interceptors

Interceptors allow you to run your code or modify requests and responses before they are handled by `then` or `catch`. This is useful for tasks like logging, authentication, and error handling.

#### Request Interceptors

A request interceptor can be used to modify requests before they are sent:

```typescript
import axios from 'axios';

// Add a request interceptor
axios.interceptors.request.use(
  config => {
    console.log('Request:', config);
    // Modify the request config if needed
    return config;
  },
  error => {
    // Handle the request error
    return Promise.reject(error);
  }
);
```

In this example, we log the request configuration before it is sent. You can also modify the configuration, such as adding authentication tokens.

#### Response Interceptors

A response interceptor can be used to handle responses globally:

```typescript
import axios from 'axios';

// Add a response interceptor
axios.interceptors.response.use(
  response => {
    console.log('Response:', response);
    // Modify the response if needed
    return response;
  },
  error => {
    // Handle the response error
    console.error('Response Error:', error);
    return Promise.reject(error);
  }
);
```

In this example, we log the response and handle any errors that occur.

### Error Handling with Axios

Handling errors is an essential part of working with HTTP requests. Axios provides a straightforward way to handle errors using `try`/`catch` blocks and response interceptors.

#### Handling Errors in Requests

You can handle errors in individual requests using `try`/`catch`:

```typescript
import axios from 'axios';

// Define a function to fetch data with error handling
async function fetchData(url: string): Promise<void> {
  try {
    const response = await axios.get(url);
    console.log('Data:', response.data);
  } catch (error) {
    if (axios.isAxiosError(error)) {
      console.error('Axios Error:', error.message);
    } else {
      console.error('Unexpected Error:', error);
    }
  }
}

// Call the function with a URL
fetchData('https://jsonplaceholder.typicode.com/posts');
```

In this example, we use `axios.isAxiosError()` to check if the error is an Axios error and log the appropriate message.

#### Global Error Handling with Interceptors

You can also handle errors globally using response interceptors:

```typescript
import axios from 'axios';

// Add a response interceptor for global error handling
axios.interceptors.response.use(
  response => response,
  error => {
    if (axios.isAxiosError(error)) {
      console.error('Global Axios Error:', error.message);
    } else {
      console.error('Global Unexpected Error:', error);
    }
    return Promise.reject(error);
  }
);
```

In this example, we handle errors globally by adding a response interceptor. This allows you to manage errors consistently across your application.

### Typing Axios Responses

TypeScript allows you to define the shape of the data you expect from an API, providing better type safety and code completion.

#### Defining Response Types

You can define a TypeScript interface to represent the response data:

```typescript
// Define an interface for the response data
interface Post {
  userId: number;
  id: number;
  title: string;
  body: string;
}

// Define a function to fetch posts with typed responses
async function fetchPosts(url: string): Promise<Post[]> {
  try {
    const response = await axios.get<Post[]>(url);
    return response.data;
  } catch (error) {
    console.error('Error fetching posts:', error);
    return [];
  }
}

// Call the function with a URL
fetchPosts('https://jsonplaceholder.typicode.com/posts').then(posts => {
  posts.forEach(post => console.log(post.title));
});
```

In this example, we define a `Post` interface and use it to type the response data. This ensures that the data we receive matches the expected structure.

### Try It Yourself

Now that you've learned the basics of using Axios with TypeScript, try modifying the examples to experiment with different configurations and request types. Here are a few ideas:

- **Add Authentication**: Modify the headers to include an authentication token.
- **Handle Pagination**: Implement logic to handle paginated API responses.
- **Use Cancel Tokens**: Explore Axios's cancellation feature to abort requests.

### Summary

In this section, we've covered the essentials of using Axios for HTTP requests in TypeScript. We've learned how to install and set up Axios, make various types of requests, configure headers, use interceptors, handle errors, and type responses. Axios provides a powerful and flexible way to handle HTTP requests, making it a valuable tool for any TypeScript developer.

## Quiz Time!

{{< quizdown >}}

### What is one advantage of using Axios over the `fetch` API?

- [x] Automatic JSON transformation
- [ ] Built-in support for WebSockets
- [ ] Requires no installation
- [ ] Only works in modern browsers

> **Explanation:** Axios automatically transforms JSON data, making it easier to work with API responses.

### How do you install Axios and its type definitions using npm?

- [x] `npm install axios @types/axios`
- [ ] `npm install axios`
- [ ] `npm install axios-types`
- [ ] `npm install axios --types`

> **Explanation:** You need to install both Axios and its type definitions using `npm install axios @types/axios`.

### Which method is used to make a GET request with Axios?

- [x] `axios.get()`
- [ ] `axios.fetch()`
- [ ] `axios.request()`
- [ ] `axios.retrieve()`

> **Explanation:** The `axios.get()` method is used to make a GET request.

### How can you set custom headers for an Axios request?

- [x] By using the `headers` option in the request configuration
- [ ] By modifying the URL
- [ ] By using a separate `setHeaders()` function
- [ ] By changing the HTTP method

> **Explanation:** Custom headers can be set using the `headers` option in the request configuration.

### What is the purpose of Axios interceptors?

- [x] To modify requests or responses before they are handled
- [ ] To cancel requests
- [ ] To log all HTTP traffic
- [ ] To automatically retry failed requests

> **Explanation:** Interceptors allow you to modify requests or responses before they are handled by `then` or `catch`.

### How can you handle errors globally in Axios?

- [x] By using response interceptors
- [ ] By wrapping every request in a `try`/`catch` block
- [ ] By using a global error handler function
- [ ] By setting a global error flag

> **Explanation:** Response interceptors can be used to handle errors globally in Axios.

### What TypeScript feature allows you to define the shape of the data you expect from an API?

- [x] Interfaces
- [ ] Enums
- [ ] Classes
- [ ] Functions

> **Explanation:** Interfaces in TypeScript allow you to define the shape of the data you expect from an API.

### How can you create an Axios instance with a base URL?

- [x] By using `axios.create({ baseURL: '...' })`
- [ ] By setting a global variable
- [ ] By modifying the default Axios instance
- [ ] By using the `baseURL` option in each request

> **Explanation:** You can create an Axios instance with a base URL using `axios.create({ baseURL: '...' })`.

### What method is used to check if an error is an Axios error?

- [x] `axios.isAxiosError()`
- [ ] `axios.isError()`
- [ ] `axios.checkError()`
- [ ] `axios.validateError()`

> **Explanation:** The `axios.isAxiosError()` method is used to check if an error is an Axios error.

### True or False: Axios supports request cancellation.

- [x] True
- [ ] False

> **Explanation:** Axios supports request cancellation, which is useful for aborting requests that are no longer needed.

{{< /quizdown >}}

## What is Node.js?

**Answer:** Node.js is an open-source, cross-platform JavaScript runtime environment that executes JavaScript code outside a web browser, often used for building scalable server-side applications.

```javascript
// Basic Node.js server
const http = require('http');
const server = http.createServer((req, res) => {
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  res.end('Hello, Node.js!');
});
server.listen(3000, () => {
  console.log('Server is running on port 3000');
});
```

## What is the difference between Node.js and JavaScript in the browser?

**Answer:** JavaScript in the browser is used for client-side tasks such as DOM manipulation, while Node.js is used for server-side programming, file handling, networking, and more.

## What are Node.js modules?

**Answer:** Modules are reusable blocks of code in Node.js, and can be built-in (like `fs` and `http`), third-party, or user-defined.

```javascript
// Importing a built-in module
const fs = require('fs');
```

## What is npm in Node.js?

**Answer:** npm (Node Package Manager) is the default package manager for Node.js, used to install, update, and manage dependencies in Node.js projects.

npm install express

## What is `package.json` and why is it important?

**Answer:** `package.json` is the configuration file for a Node.js project, which holds metadata about the project and manages its dependencies.

## What is Event-Driven Architecture in Node.js?

**Answer:** Node.js follows an event-driven architecture where asynchronous operations are handled using events and callbacks.

```javascript
const EventEmitter = require('events');
const emitter = new EventEmitter();
emitter.on('event', () => {
  console.log('Event triggered!');
});
emitter.emit('event');
```

## What is the `EventEmitter` in Node.js?

**Answer:** The `EventEmitter` class is a core module that facilitates communication through events in Node.js applications.

## What are Streams in Node.js?

**Answer:** Streams are objects in Node.js that allow reading and writing data in chunks rather than buffering it all in memory. They are useful for handling large files.

```javascript
const fs = require('fs');
const readStream = fs.createReadStream('file.txt');
readStream.on('data', (chunk) => {
  console.log(chunk.toString());
});
```

## Explain the `fs` module in Node.js.

**Answer:** The `fs` module provides methods for interacting with the file system, such as reading and writing files.

```javascript
const fs = require('fs');
fs.readFile('file.txt', 'utf8', (err, data) => {
  if (err) throw err;
  console.log(data);
});
```

## What is middleware in Node.js?

**Answer:** Middleware is a function that has access to the request object (`req`), response object (`res`), and the next middleware function in the request-response cycle.

```javascript
const express = require('express');
const app = express();

app.use((req, res, next) => {
  console.log('Middleware executed');
  next();
});
```

## What is the difference between `require()` and `import` in Node.js?

**Answer:** `require()` is the CommonJS module system used in Node.js, while `import` is used in ES6 module syntax, which is more modern and has stricter loading behavior.

## How does Node.js handle concurrency?

**Answer:** Node.js handles concurrency using an event loop and non-blocking I/O operations, allowing it to handle many requests at once without multi-threading.

## What is the Event Loop in Node.js?

**Answer:** The event loop is the mechanism that allows Node.js to perform non-blocking, asynchronous operations by offloading tasks to the operating system.

## What is a callback in Node.js?

**Answer:** A callback is a function passed as an argument to another function, which is executed after an asynchronous operation is completed.

```javascript
fs.readFile('file.txt', (err, data) => {
  if (err) throw err;
  console.log(data.toString());
});
```

## What is `process` in Node.js?

**Answer:** The `process` object in Node.js provides information about the current Node.js process, such as environment variables, and allows developers to interact with the system.

console.log(process.env);

## What is the difference between process.nextTick() and setImmediate()?

**Answer:** `process.nextTick()` queues the callback to be invoked in the current phase of the event loop, whereas `setImmediate()` schedules it for the next iteration of the event loop.

## What is cluster module in Node.js?

**Answer:** The cluster module allows you to create child processes (workers) that share the same server port, enabling the handling of multiple requests in parallel.

```javascript
const cluster = require('cluster');
const http = require('http');

if (cluster.isMaster) {
  cluster.fork();
} else {
  http
    .createServer((req, res) => {
      res.writeHead(200);
      res.end('Handled by worker');
    })
    .listen(8000);
}
```

## What are Buffers in Node.js?

**Answer:** Buffers are used to handle binary data in Node.js, especially when dealing with streams and file operations.

```javascript
const buffer = Buffer.from('Hello');
console.log(buffer.toString()); // Outputs: Hello
```

## How do you handle errors in Node.js?

**Answer:** Error handling in Node.js is typically done by passing errors to callback functions or using `try...catch` blocks with promises or async/await.

```javascript
fs.readFile('file.txt', (err, data) => {
  if (err) {
    console.error('Error reading file', err);
  } else {
    console.log(data.toString());
  }
});
```

## What are Promises in Node.js?

**Answer:** Promises represent the eventual completion (or failure) of an asynchronous operation and allow you to chain operations.

```javascript
const promise = new Promise((resolve, reject) => {
  setTimeout(() => resolve('Done!'), 1000);
});

promise.then((result) => console.log(result)); // Outputs: Done!
```

## What is async/await in Node.js?

**Answer:** `async`/`await` is syntactic sugar built on top of promises, making asynchronous code look synchronous and easier to read.

```javascript
async function fetchData() {
  const result = await fetch('https://api.example.com');
  console.log(await result.json());
}
```

## What is the difference between synchronous and asynchronous methods in Node.js?

**Answer:** Synchronous methods block the execution of further code until they complete, while asynchronous methods allow other operations to run while waiting for the current one to finish.

```javascript
// Synchronous
const data = fs.readFileSync('file.txt');

// Asynchronous
fs.readFile('file.txt', (err, data) => {
  if (err) throw err;
  console.log(data.toString());
});
```

## What is Express.js?

**Answer:** Express.js is a popular web application framework for Node.js that simplifies the process of building web servers and APIs.

```javascript
const express = require('express');
const app = express();

app.get('/', (req, res) => res.send('Hello World!'));

app.listen(3000, () => console.log('Server is running on port 3000'));
```

## What is middleware in Express.js?

**Answer:** Middleware in Express.js is a function that can modify the request or response, perform logging, handle errors, etc., and pass control to the next middleware.

```javascript
app.use((req, res, next) => {
  console.log('Middleware called');
  next();
});
```

## How do you secure a Node.js application?

**Answer:** Some best practices include using HTTPS, validating input data, protecting against SQL injection, securing dependencies, and using tools like Helmet for HTTP headers security.

```javascript
const helmet = require('helmet');
app.use(helmet());
```

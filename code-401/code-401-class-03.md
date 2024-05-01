# Readings: Express REST API

Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.
Review the Submission Instructions for guidance on completing and submitting this assignment.
Readings
Review: ES6 Classes

## Classes are a template for creating ____

Classes are a template for creating objects.

## Can a class declaration be hoisted?

In JavaScript, class declarations are not hoisted like function declarations. This means that you cannot reference a class before it is declared in the code. When you declare a class using the `class` keyword, its definition is not hoisted to the top of its scope. Therefore, you need to define a class before you can use it.

## How would you describe a constructor and contextual “this” to a non-technical friend?

Imagine you're building a house using a blueprint. The constructor is like the blueprint itself. It's a set of instructions that tells you how to build the house. Now, the "this" keyword is like a magic pointer that helps you refer to different parts of the house while you're building it.
So, when you're following the blueprint (constructor) to build the house (object), you might come across something like "this door" or "this window." The "this" keyword helps you understand that you're talking about the door or window of the house you're currently building, not some other house.
In simpler terms, the constructor is the plan for making something, and "this" helps you keep track of what you're currently working on within that plan.

Using Express Routing

## Within Express, what does routing refer to?

In Express, routing refers to the process of determining how an application responds to a client request to a particular endpoint (URL) and HTTP method (GET, POST, etc.). It involves defining routes that map specific URLs to functions (route handlers) that are executed when the server receives a request to that URL.
For example, if a client makes a GET request to the '/products' endpoint of your Express application, you can define a route handler to handle that request. Within this route handler, you might retrieve a list of products from a database and send it back as a response to the client.
Routing in Express allows you to organize your application's logic and handle different types of requests to different endpoints effectively.

## What is the difference between a route path and a route method?

In Express, the route path and the route method are two distinct components used to define routes for handling HTTP requests.

1. Route Path:
   - The route path specifies the URL pattern or endpoint at which a route handler should respond.
   - It can be a string, a string pattern, or a regular expression.
   - It represents the part of the URL after the domain name.
   - For example, '/products' or '/users/:id' are route paths.
2. Route Method:
   - The route method specifies the HTTP method (such as GET, POST, PUT, DELETE, etc.) that the route handler should respond to.
   - It determines the type of request the route handler will handle.
   - For example, `app.get()` sets up a route handler for GET requests, `app.post()` for POST requests, and so on.
In summary, the route path defines the URL pattern, while the route method specifies the type of HTTP request that should trigger the route handler. Together, they form the complete definition of a route in an Express application.

## When is it appropriate to add next as a parameter to a route handler and what must you do if next has been passed to your middleware as a parameter?

In Express, the `next` parameter is typically used in route handlers and middleware to pass control to the next middleware function in the stack. It's appropriate to add `next` as a parameter to a route handler when you want to delegate control to the next middleware or route handler in the chain.
You might use `next` in a route handler when you need to perform asynchronous operations, such as database queries or API requests, and you want to ensure that the next middleware or route handler is called only after these operations have completed.
If `next` has been passed to your middleware as a parameter, you must call it within your middleware to pass control to the next middleware function in the stack. If you forget to call `next`, the request will hang, and the Express application won't proceed to the next middleware or route handler.
Here's an example of how you would use `next` in a middleware function:

function myMiddleware(req, res, next) {
    // Do something...
    next(); // Call next to pass control to the next middleware or route handler
}
app.use(myMiddleware);

And here's an example of using `next` in a route handler:
app.get('/example', function(req, res, next) {
    // Do something...
    next(); // Call next to pass control to the next middleware or route handler
}, function(req, res) {
    // This will be executed after the previous middleware
    res.send('Response');
});
In both cases, `next()` is called to pass control to the next middleware function or route handler in the chain.

Express Routing

## What is an Express Router?

An Express Router is a feature of the Express.js web application framework that allows you to group related routes and middleware into modular, reusable units.

In Express, as your application grows, you may have many routes and middleware functions, which can make your main application file quite lengthy and complex. Express Router helps you organize your routes and middleware into separate files or modules, making your codebase more maintainable and easier to understand.

You can create an instance of a router using `express.Router()`, and then define routes and middleware on that router using methods like `router.get()`, `router.post()`, `router.use()`, etc. Once you've defined your routes and middleware on the router, you can mount the router on your main Express application using `app.use()`.
Here's a simple example of how you might use an Express Router:
// routes/user.js
const express = require('express');
const router = express.Router();
router.get('/', function(req, res) {
    res.send('User list');
});
router.get('/:id', function(req, res) {
    res.send('User details for ID: ' + req.params.id);
});
module.exports = router;
// app.js
const express = require('express');
const userRouter = require('./routes/user');
const app = express();
app.use('/users', userRouter);
app.listen(3000, () => {
    console.log('Server is running on port 3000');
});
In this example, we've defined routes for handling user-related requests in a separate file (`routes/user.js`). We created an Express Router instance, defined routes on it, and exported the router. Then, in our main application file (`app.js`), we imported the user router and mounted it on the '/users' path using `app.use()`. This allows us to keep our code organized and modular.

## By what mean do we initialize express.Router() in an express server?

To initialize an Express Router in an Express server, you simply call the `express.Router()` method. This creates a new instance of a router.
const express = require('express');
const router = express.Router();
Once you have initialized the router, you can define routes and middleware on it using methods like `router.get()`, `router.post()`, `router.use()`, etc.
Here's a basic example of initializing and using a router:
// Initialize Express
const express = require('express');
const app = express();
// Initialize Router
const router = express.Router();
// Define a route on the router
router.get('/', function(req, res) {
    res.send('Hello from the router!');
});
// Mount the router on a specific path in the Express app
app.use('/example', router);
// Start the server
app.listen(3000, () => {
    console.log('Server is running on port 3000');
});
In this example, we've initialized an Express app (`app`) and a router (`router`). We defined a route on the router that responds with "Hello from the router!" when the client makes a GET request to the root path ('/'). Then, we mounted the router on the '/example' path in the Express app using `app.use()`. So, when a client makes a request to '/example', the router's route handler will be invoked.

## What do we use route middleware for?

Route middleware in Express is used for a variety of purposes, including:

1. **Authentication**: Middleware can be used to authenticate incoming requests before they reach the route handler. This ensures that only authenticated users can access certain routes or resources.

2. **Authorization**: Middleware can also be used for authorization purposes, determining whether an authenticated user has the necessary permissions to access a particular route or resource.
3. **Request preprocessing**: Middleware functions can preprocess incoming requests by parsing request bodies, validating input data, or performing other necessary operations before passing control to the route handler.
4. **Logging**: Middleware can log information about incoming requests, such as request method, URL, and timestamp. This can be useful for debugging and monitoring purposes.
5. **Error handling**: Middleware can handle errors that occur during request processing. For example, middleware can catch errors thrown by route handlers and return appropriate error responses to clients.
6. **Caching**: Middleware can implement caching mechanisms to improve performance by caching responses for certain routes and serving cached responses to subsequent requests.
7. **Rate limiting**: Middleware can enforce rate limiting policies to prevent abuse or excessive usage of API endpoints by limiting the number of requests allowed from a single client within a certain time period.
Overall, route middleware provides a flexible and powerful mechanism for adding additional functionality and behavior to routes in an Express application. It allows for modular, reusable code and helps keep route handlers clean and focused on handling business logic specific to each route.

Reflection

## What are your learning goals after reading and reviewing the class README?

After reading and reviewing the class README, my learning goals would be:

1. Understanding the concept of external routing with Express and how to implement it using `express.Router()`.
2. Mastering the CRUD operations (CREATE, READ, UPDATE, DELETE) with REST and Express, and knowing how to define routes for each operation.
3. Becoming proficient in using Sequelize for interacting with a SQL database, including setting up database configuration, defining models and schemas, and performing basic SQL operations like creating, reading, updating, and deleting records.
4. Learning how to structure Express applications in a modular and organized way to improve maintainability and scalability.
5. Gaining familiarity with testing Express routes and code that relies on a PostgreSQL database, including setting up test environments and writing test cases.
6. Acquiring knowledge about deploying a PostgreSQL database in the cloud and connecting it to an Express application, including managing environment variables and ensuring secure connections.

Overall, my goal is to gain a comprehensive understanding of building RESTful APIs with Express, integrating with databases using Sequelize, and deploying applications using cloud services.

# Reading-Notes 12

Readings: CRUD

Below you will find some reading material, code samples, and some additional resources that support the topic for this class and the upcoming lecture.
Review the Submission Instructions for guidance on completing and submitting this assignment.
 Reading
Status Codes Based On REST Methods

## 1. In your own words, describe what each group of status code represents

HTTP status codes are three-digit numbers returned by a web server in response to a client's request. They provide information about the status of the request. Here's what each group of status codes generally represents:
100's = Informational Responses: These status codes indicate that the server has received the request and is continuing the process. They are typically interim responses used to inform the client that the request is being received and processed.
200's = Success Responses: These status codes indicate that the client's request was successfully received, understood, and accepted by the server. They confirm that the requested action has been completed successfully.
300's = Redirection Responses: These status codes indicate that further action is needed to complete the request. They often inform the client that the requested resource has been moved to a different location, and they provide instructions on how to proceed.
400's = Client Error Responses: These status codes indicate that there was an error on the client's side, such as a malformed request or unauthorized access. They signify that the server cannot process the request due to client-side issues.
500's = Server Error Responses: These status codes indicate that there was an error on the server side while trying to fulfill the request. They signify that the server encountered an unexpected condition that prevented it from fulfilling the request made by the client.

## 2. What is a status code 202?

HTTP status code 202, known as "Accepted," indicates that the request has been accepted for processing, but the processing has not been completed. This status code is often used in scenarios where the server needs more time to fulfill the request, or the processing of the request has been queued for future execution. It does not necessarily mean that the request was successful or that the action requested by the client has been completed. Instead, it signifies that the server has received the request and intends to process it at some point in the future.

## 3. What is a status code 308?

HTTP status code 308, known as "Permanent Redirect," indicates that the resource requested by the client has been permanently moved to a different URL. This status code informs the client to update its links to the new URL permanently, as further requests for the original URL should be directed to the new location.
Similar to the more commonly known status code 301 (Moved Permanently), the 308 status code indicates that the redirection is permanent and should be cached by the client for future requests. However, unlike the 301 status code, which allows the request method to be changed from POST to GET, the 308 status code requires that the method and body of the original request be retained for subsequent requests to the new URL. This ensures that the client's request is properly redirected without losing any data.

## 4. What code would you use if an update didn’t return data to a client?

If an update operation was successfully performed on the server but did not return any data to the client, the appropriate HTTP status code to use would be 204 No Content.
HTTP status code 204 indicates that the server has successfully processed the request and that there is no content to send in the response payload. It is typically used in scenarios where the client does not need to receive any data back from the server after performing an operation, such as updating a resource.
Using the 204 status code informs the client that the update was successful without cluttering the response with unnecessary data. This can help improve network efficiency and reduce unnecessary bandwidth usage.

## 5. What code would you use if a resource used to exist but no longer does?

If a resource that used to exist no longer does, the appropriate HTTP status code to use is 410 Gone.
HTTP status code 410 indicates that the requested resource is no longer available at the server and that there is no forwarding address. It differs from status code 404 (Not Found) in that 404 indicates that the server cannot locate the requested resource, but it does not necessarily mean that the resource has been permanently removed. In contrast, status code 410 specifically indicates that the resource is gone and is not expected to be available again.
Using the 410 status code informs clients that the requested resource has been intentionally removed and allows them to take appropriate action, such as updating their bookmarks or removing links to the resource. It provides a clear indication that the resource is no longer accessible, helping to prevent unnecessary future requests for the same resource.

## 6. What is the ‘Forbidden’ status code?

The "Forbidden" status code in HTTP is represented by code 403. It indicates that the server understood the request from the client, but the server is refusing to fulfill it due to insufficient permissions or authorization. Essentially, the server is telling the client that the requested action cannot be completed because the client does not have the necessary permissions to access the resource or perform the requested operation.
When a client receives a 403 Forbidden response, it typically means that the server has recognized the client's identity, but the client lacks the necessary credentials or permissions to access the requested resource. This status code is often used to protect sensitive information or resources from unauthorized access.
In summary, the 403 Forbidden status code signifies that the client's request has been understood by the server, but the server is refusing to fulfill it due to lack of authorization or permissions.
Videos
Build A REST API With Node.js, Express, & MongoDB - Quick - First 20 minutes

## 1. Why do we need to pull our MongoDB database string out of our server and put it into our .env?

Pulling the MongoDB database string out of the server and putting it into the .env file is a security best practice known as environment variable configuration. There are several reasons why this approach is preferred:

1. **Security**: Storing sensitive information, such as database connection strings, directly in server-side code exposes it to potential security vulnerabilities. If the code is accidentally exposed or accessed by unauthorized users, they could gain access to critical database credentials. Placing these sensitive details in a separate .env file helps mitigate this risk because .env files are typically not exposed publicly.
2. **Portability**: By storing configuration details in environment variables, the application becomes more portable. Developers can easily deploy the application to different environments (development, staging, production) without modifying the code. Each environment can have its own .env file with appropriate configuration values.
3. **Ease of Management**: Managing configuration settings, such as database connection strings, becomes more manageable when stored in environment variables. Developers can update configuration values in the .env file without having to modify the source code. This separation of concerns simplifies maintenance and reduces the risk of introducing errors during code changes.
4. **Scalability**: As applications grow and evolve, the number of configuration settings may increase. Storing these settings in environment variables keeps the codebase clean and organized, making it easier to scale and maintain over time.

Overall, using environment variables for sensitive configuration details, such as database connection strings, enhances security, portability, ease of management, and scalability of the application. It's considered a best practice in modern application development.

## 2. What is middleware?

Middleware is a software component that acts as a bridge or intermediary between different parts of an application or between an application and an external system. It intercepts incoming requests, performs specific actions, and then passes the request to the next middleware component or the main application logic.
In web development, middleware is commonly used in frameworks like Express.js (for Node.js) or Django (for Python). Middleware functions have access to the request and response objects as well as the next middleware function in the chain.
Middleware functions can be used for a variety of purposes, including:

1. **Request Processing**: Middleware can preprocess incoming requests by parsing request data, validating input, or attaching additional data to the request object before passing it to the main application logic.
2. **Authentication and Authorization**: Middleware can enforce security measures by verifying user authentication tokens, checking user permissions, or restricting access to certain routes based on user roles.
3. **Logging and Error Handling**: Middleware can log request details, monitor application performance, or handle errors by catching exceptions and returning appropriate error responses to clients.
4. **Caching and Compression**: Middleware can implement caching mechanisms to improve performance by storing frequently accessed data in memory or by compressing response data to reduce bandwidth usage.
5. **Routing and Redirects**: Middleware can handle URL routing, route redirection, or URL rewriting by inspecting incoming request URLs and directing traffic to the appropriate route or endpoint.
6. **Content Transformation**: Middleware can modify request or response content by parsing request bodies, transforming data formats (e.g., JSON to XML), or compressing response payloads.

Overall, middleware plays a crucial role in modern web applications by providing a flexible and modular approach to handling common tasks and cross-cutting concerns. It promotes code reuse, improves maintainability, and enhances the overall performance and security of the application.

## 3. What does app.use(express.json()) do?\

In an Express.js application, `app.use(express.json())` is middleware that parses incoming request bodies with JSON payloads.
When a client sends a POST or PUT request to the server with a JSON payload in the request body, `express.json()` middleware intercepts the request, parses the JSON data, and then attaches it to the `req.body` property of the request object. This makes it easier for developers to access and work with the JSON data within their route handlers or middleware functions.
Here's a breakdown of what `app.use(express.json())` does:

1. **Intercepts Requests**: Whenever a request is made to the Express server, `express.json()` middleware intercepts the incoming request before it reaches the route handler or other middleware.
2. **Parses JSON Data**: If the request contains a JSON payload in its body, `express.json()` parses the JSON data and converts it into a JavaScript object.
3. **Attaches Parsed Data to `req.body`**: The parsed JSON data is then attached to the `req.body` property of the request object. This allows developers to access the parsed JSON data within their route handlers or subsequent middleware functions.

By using `app.use(express.json())`, developers can easily handle JSON data sent from clients without manually parsing the request body. It simplifies the process of working with JSON data in Express.js applications and promotes cleaner and more concise code.

## 4. What does the /:id mean in a route?

In Express.js, the `/` followed by `:id` in a route pattern represents a route parameter.
When a client makes a request to a route with this pattern, such as `/users/:id`, Express.js treats the part after the colon (`:`) as a placeholder for a dynamic value. This dynamic value can vary depending on the specific request.
For example, in the route `/users/:id`, `:id` represents the ID of a user. When a request is made to this route, the actual user ID will replace `:id` in the route. For instance, a request to `/users/123` would match the route pattern and `req.params.id` would be equal to `123`.
Route parameters are accessible in Express.js route handlers via the `req.params` object. In the case of `/users/:id`, the value of the `id` parameter can be accessed within the route handler using `req.params.id`.
Using route parameters allows developers to create dynamic routes that can handle different data or resources based on the values provided in the URL. This makes Express.js applications more flexible and powerful, enabling developers to create RESTful APIs and handle various types of requests efficiently.

## 5. What is the difference between PUT and PATCH?

`PUT` and `PATCH` are both HTTP methods used for updating resources on the server, but they have different semantics and usage scenarios:

1. **PUT**:
   - `PUT` is used to update or replace an entire resource or resource representation at a specific URI.
   - When a client sends a `PUT` request, it typically includes the complete new representation of the resource in the request body.
   - The server then replaces the existing resource at the specified URI with the new representation provided in the request body.
   - If the resource does not exist at the specified URI, `PUT` may create a new resource. However, it's important to note that `PUT` is idempotent, meaning that multiple identical `PUT` requests will have the same effect as a single request. Therefore, if a resource already exists at the specified URI, `PUT` will overwrite it with the new representation.
2. **PATCH**:
   - `PATCH` is used to apply partial modifications to a resource or resource representation.
   - Unlike `PUT`, which replaces the entire resource, `PATCH` allows clients to send a partial representation of the resource with only the changes that need to be applied.
   - The server then applies the provided changes to the existing resource, modifying only the specified fields or properties while leaving the rest of the resource unchanged.
   - `PATCH` requests are often used when clients want to update specific fields or properties of a resource without having to send the entire representation, which can be more efficient in terms of network bandwidth and server processing.
   - `PATCH` is also idempotent, meaning that multiple identical `PATCH` requests will produce the same result as a single request. However, unlike `PUT`, `PATCH` requests are not required to be idempotent by the HTTP specification.

In summary, `PUT` is used to replace the entire resource, while `PATCH` is used to apply partial modifications to a resource. `PUT` is typically used when clients have the complete new representation of the resource, whereas `PATCH` is used when clients want to apply specific changes to an existing resource.

## 6. How do you make a default value in a schema?

In Mongoose, which is an Object Data Modeling (ODM) library for MongoDB and Node.js, you can set default values for fields in a schema using the `default` property. Here's how you can define a default value for a field in a Mongoose schema:
javascript
const mongoose = require('mongoose');
// Define the schema
const userSchema = new mongoose.Schema({
  name: {
    type: String,
    required: true
  },
  age: {
    type: Number,
    default: 18 // Default value for age field
  },
  email: {
    type: String,
    required: true
  }
});
// Create a model based on the schema
const User = mongoose.model('User', userSchema);
// Example usage:
const newUser = new User({
  name: 'John Doe',
  email: ( 'john@example .com' )
});
console.log(newUser); // Output: { name: 'John Doe', age: 18, email: 'john@example .com' }

In the above example:

- The `age` field in the `userSchema` has a default value of `18`. If no value is provided for `age` when creating a new document, it will default to `18`.
- When creating a new instance of the `User` model, if the `age` field is not provided, it will default to `18` as specified in the schema.

This allows you to ensure that certain fields have default values even if they are not explicitly provided when creating new documents.

## 7. What does a 500 error status code mean?

A 500 Internal Server Error status code indicates that the server encountered an unexpected condition that prevented it from fulfilling the client's request. This error is a generic "catch-all" status code used to indicate that something has gone wrong on the server side, but the server is unable to provide more specific information about the nature of the problem.
Some common causes of a 500 Internal Server Error include:

1. **Server-side code errors**: This could be due to a bug or syntax error in the server-side code, causing it to malfunction when processing the request.
2. **Database errors**: If the server encounters issues while interacting with the database, such as connection failures, query errors, or data corruption, it may result in a 500 error.
3. **Configuration issues**: Misconfigurations in server settings, such as incorrect file permissions, invalid directives in configuration files, or missing dependencies, can lead to server errors.
4. **Resource exhaustion**: If the server runs out of memory, disk space, or other resources required to fulfill the request, it may result in a 500 error.
5. **Unexpected exceptions**: Certain unexpected conditions or exceptions occurring during the execution of server-side code, such as out-of-bounds errors or unhandled exceptions, can lead to a 500 error.

When a client receives a 500 Internal Server Error, it indicates that the problem lies with the server and not with the client's request. Typically, this error is logged on the server side to help administrators diagnose and troubleshoot the underlying issue. Users encountering a 500 error are often advised to try again later or contact the website or service administrator for assistance.

## 8. What is the difference between a status 200 and a status 201?

The main difference between a status code 200 and a status code 201 lies in their respective meanings and intended use cases:

1. **Status Code 200 (OK)**:
   - Status code 200 indicates that the client's request was successful and that the server has successfully processed the request.
   - It is the standard response for successful HTTP requests where the server returns a payload containing the requested resource.
   - Status code 200 is typically used for GET requests to retrieve resources, POST requests to create new resources, PUT requests to update existing resources, and DELETE requests to remove resources.
2. **Status Code 201 (Created)**:
   - Status code 201 indicates that the request has been fulfilled and that a new resource has been successfully created as a result of the request.
   - It is typically used in response to successful POST requests where the server creates a new resource based on the information provided in the request body.
   - Along with the 201 status code, the server typically includes a `Location` header in the response, specifying the URL of the newly created resource.
   - Status code 201 is useful for indicating to the client that the requested operation (e.g., resource creation) was successful and that a new resource is now available at the provided location.
In summary, while both status code 200 and status code 201 indicate successful responses from the server, status code 200 is more general and used for various types of successful requests, whereas status code 201 specifically indicates that a new resource has been created in response to a POST request.

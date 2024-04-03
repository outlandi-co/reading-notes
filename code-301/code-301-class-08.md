# Reading-Notes 8

API Design Best Practices

## 1. What does REST stand for?

REST stands for Representational State Transfer. It is an architectural style for designing networked applications. RESTful systems typically use HTTP as the communication protocol, and they emphasize simplicity, scalability, and the concept of statelessness.

## 2. REST APIs are designed around a ____

REST APIs are designed around a resource-oriented architecture. In RESTful design, resources are the key abstractions, and APIs are built to allow clients to interact with these resources through standard HTTP methods (such as GET, POST, PUT, DELETE) and representations (such as JSON or XML). Each resource is identified by a unique URI (Uniform Resource Identifier), and clients can perform various actions on these resources by sending requests to their corresponding URIs.

## 3. What is an identifier of a resource? Give an example

An identifier of a resource is a unique string or address used to locate and access that particular resource within a system. In the context of RESTful APIs, Uniform Resource Identifiers (URIs) serve as identifiers for resources. These URIs typically follow a hierarchical structure and can include various components to identify the resource.
Here's an example of a URI identifying a resource:

`https://api.example.com/products/12345`

In this example:

- `https://api.example.com` is the base URL of the API.

- `/products` is the endpoint or resource collection representing a group of products.
- `/12345` is a unique identifier (in this case, it could be the product ID) specifying a specific product within the collection.
So, in this URI, `/products/12345` uniquely identifies a particular product resource within the system.

## 4. What are the most common HTTP verbs?

The most common HTTP verbs, also known as HTTP methods, are:

1. **GET**: Used to retrieve data from a server. It should not have any other effect.
2. **POST**: Used to submit data to be processed to a specified resource. It can also result in the creation of a new resource.
3. **PUT**: Used to update or replace the data of a specific resource identified by the URI.
4. **DELETE**: Used to delete the specified resource from the server.
5. **PATCH**: Used to apply partial modifications to a resource.
These HTTP methods form the basis of CRUD (Create, Read, Update, Delete) operations in RESTful APIs and web applications.

## 5. What should the URIs be based on?

URIs (Uniform Resource Identifiers) in RESTful APIs should be based on the resources they represent. In other words, the structure of URIs should reflect the logical hierarchy and relationships between the resources in the system.
Here are some principles to consider when designing URIs for RESTful APIs:

1. **Resource-Oriented**: URIs should represent resources, not actions. Each
URI should identify a unique resource in the system.
2. **Hierarchy**: URIs should be structured hierarchically to reflect the relationships between resources. For example, a URI for a specific resource could include segments representing parent resources or categories.
3. **Consistency**: URIs should follow consistent naming conventions and patterns throughout the API. This makes it easier for developers to understand and navigate the API.
4. **Readability**: URIs should be human-readable and intuitive whenever possible. They should convey meaningful information about the resource they represent.
5. **Stability**: URIs should remain stable over time to ensure backward compatibility. Changing URIs can break existing client applications and cause maintenance issues.
Overall, the design of URIs in RESTful APIs should prioritize clarity, consistency, and adherence to RESTful principles to enhance the usability and maintainability of the API.

## 6. Give an example of a good URI

Sure, here's an example of a well-structured URI for a hypothetical RESTful API that manages products:

`https://api.example.com/products/12345`

In this example:

- `https://api.example.com` is the base URL of the API.

- `/products` represents the collection of products in the system.
- `/12345` is the unique identifier (such as a product ID) that identifies a specific product within the collection.

This URI follows the principles of RESTful design:

1. It is resource-oriented, with `/products` representing the resource collection and `/12345` representing a specific resource (a product).
2. It has a hierarchical structure, with `/products` as the parent resource and `/12345` as a child resource.
3. It is readable and intuitive, clearly indicating that it deals with products and provides a unique identifier for a specific product.
4. It is stable, meaning that the URI is expected to remain consistent over time, allowing clients to rely on it for accessing the corresponding resource.

## 7. What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?

A "chatty" web API refers to an API that requires multiple requests to accomplish a single task or retrieve a set of data. This often occurs when the API's resources are designed in such a way that each resource requires separate requests to access or manipulate.
Having a chatty web API can be considered a disadvantage for several reasons:

1. **Performance Overhead**: Each request incurs overhead in terms of network latency, processing time, and potentially authentication/authorization checks. Multiple requests increase the overall time required to accomplish a task, reducing performance and responsiveness.
2. **Increased Bandwidth Usage**: Sending multiple requests results in higher bandwidth consumption, especially if the payload of each request is significant. This can lead to increased costs, particularly in scenarios where bandwidth usage is metered.
3. **Complexity**: Chatty APIs often require more complex client-side logic to manage multiple requests, handle errors, and coordinate interactions between resources. This increases the complexity of client applications and can make them harder to develop and maintain.
4. **Greater Server Load**: Handling a large number of requests puts additional load on the server, which can impact its scalability and availability, particularly under high traffic conditions.
In contrast, a "non-chatty" or "coarse-grained" API design minimizes the number of requests required to accomplish tasks by exposing more comprehensive operations and data retrieval mechanisms. This approach generally leads to better performance, reduced bandwidth usage, simpler client code, and lower server load.
Therefore, having a chatty web API is generally considered a bad thing, and it's often recommended to design APIs with coarse-grained endpoints that allow clients to accomplish tasks with fewer requests. However, the suitability of a particular API design depends on various factors, including the specific requirements of the application and the trade-offs involved.

## 8. What status code does a successful GET request return?

A successful GET request typically returns the status code 200 OK. This status code indicates that the request has succeeded, and the server has returned the requested resource. The response may include the requested data in the body of the response, depending on the specific implementation of the API.

## 9. What status code does an unsuccessful GET request return?

An unsuccessful GET request can return various status codes depending on the specific reason for the failure. Some common status codes for unsuccessful GET requests include:

1. **404 Not Found**: This status code indicates that the server could not find the requested resource. It's commonly used when the URI specified in the request does not match any resource on the server.
2. **403 Forbidden**: This status code indicates that the server understood the request but refuses to authorize it. It's typically returned when the client doesn't have permission to access the requested resource.
3. **401 Unauthorized**: This status code indicates that the request requires user authentication. It's commonly used when the client needs to provide credentials (such as a username and password) to access the resource, but the request lacks proper authentication credentials.
4. **400 Bad Request**: This status code indicates that the server cannot process the request due to invalid syntax or other client-side errors. It's often returned when the request is malformed or missing required parameters.
5. **500 Internal Server Error**: While less common for GET requests, this status code indicates that an unexpected condition was encountered on the server, preventing it from fulfilling the request. It's a general-purpose error code that doesn't provide specific details about the nature of the problem.
These are just a few examples, and there are other status codes that might be returned depending on the specific circumstances of the unsuccessful GET request. It's important for clients to handle these status codes appropriately and provide meaningful error messages to users or developers when errors occur.

## 10. What status code does a successful POST request return?

A successful POST request typically returns the status code 201 Created. This status code indicates that the request has been fulfilled and a new resource has been created as a result of the request. The response usually includes a Location header that specifies the URI of the newly created resource.

## 11. What status code does a successful DELETE request return?

A successful DELETE request typically returns the status code 204 No Content. This status code indicates that the request has been successfully processed and that there is no content to send in the response payload. However, the response may include optional headers or metadata.

Bookmark and Review
RegExr - Pay particular attention to the cheatsheet
Regex Tutorial
Regex 101

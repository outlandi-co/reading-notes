# Reading-Notes 13

 Readings: More CRUD

Below you will find some reading material, code samples, and some additional resources that support the topic for this class and the upcoming lecture.
Review the Submission Instructions for guidance on completing and submitting this assignment.
Reading
CRUD Basics

## 1. Which HTTP method would you use to update a record through an API?

To update a record through an API, you typically use the HTTP PUT or PATCH method. PUT is generally used to completely replace an existing resource with the new one provided in the request, while PATCH is used to partially update a resource with the changes provided in the request. The choice between PUT and PATCH depends on the specific requirements of your API and the semantics you want to convey.

## 2. Which REST methods require an ID parameter?

In RESTful APIs, the PUT, GET, DELETE, and PATCH methods often require an ID parameter to identify the specific resource being manipulated. Here's how each method typically uses the ID parameter:
1.**GET**: Used to retrieve a specific resource identified by its unique ID.
2.**PUT**: Used to update a resource identified by its unique ID. The ID parameter is typically used to specify which resource to update.
3.**DELETE**: Used to delete a resource identified by its unique ID.
4.**PATCH**: Used to partially update a resource identified by its unique ID. The ID parameter helps identify which resource to patch.
POST method may not require an ID parameter because it's often used to create a new resource, and the server generates the ID for the newly created resource.
Videos
Speed Coding: Building a CRUD API (Watch a Twitch streamer code an Express API in 20 minutes!)

## 1. What’s the relationship between REST and CRUD?

REST (Representational State Transfer) and CRUD (Create, Read, Update, Delete) are closely related concepts in web development, particularly in the context of building APIs.
1.**CRUD**: CRUD represents the basic operations that can be performed on data: Create, Read, Update, and Delete. These operations correspond to the basic actions that can be taken with persistent storage.
2.**REST**: REST is an architectural style for designing networked applications. It emphasizes a stateless client-server architecture where web resources are accessed and manipulated using a set of standard operations, typically through HTTP methods like GET, POST, PUT, PATCH, and DELETE.
The relationship between REST and CRUD lies in the mapping of CRUD operations to HTTP methods:

- **Create**: Corresponds to the HTTP POST method, used to create a new resource on the server.
- **Read**: Corresponds to the HTTP GET method, used to retrieve a representation of a resource.
- **Update**: Corresponds to the HTTP PUT or PATCH methods. PUT is typically used to update a resource with a complete representation, while PATCH is used to partially update a resource.
- **Delete**: Corresponds to the HTTP DELETE method, used to delete a resource from the server.
So, while CRUD represents the basic operations that can be performed on data, REST provides a standardized way of implementing these operations using HTTP methods within an API architecture.

## 2. If you had to describe the process of creating a RESTful API in 5 steps, what would they be?

Five steps to create a RESTful API:

1. **Identify Resources**: Determine what data your API will expose and define the resources that represent that data. Resources can be anything from users and products to articles and orders.
2. **Define Endpoints**: For each resource, define the endpoints that clients can interact with to perform CRUD operations (Create, Read, Update, Delete). These endpoints should be intuitive and follow RESTful principles. For example, `/users` might represent the collection of users, while `/users/{id}` represents an individual user.
3. **Choose HTTP Methods**: Assign appropriate HTTP methods (GET, POST, PUT, PATCH, DELETE) to each endpoint based on the actions they perform. Use GET for reading data, POST for creating data, PUT or PATCH for updating data, and DELETE for deleting data.
4. **Design Responses**: Determine the format of the responses your API will return. This could be JSON, XML, or another format. Ensure that responses are well-structured and contain relevant information, such as status codes and error messages.
5. **Implement and Test**: Finally, implement your API endpoints according to the defined specifications. Test each endpoint thoroughly to ensure it behaves as expected, handling various scenarios such as successful requests, validation errors, and server errors. Additionally, consider security measures like authentication and authorization during implementation.
 Code Fellows 2024

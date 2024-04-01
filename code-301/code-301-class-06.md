# Reading-Notes 6

What Google Learned From Its Quest to Build the Perfect Team
If you’ve read this before, skim this article again for a refresher.

## 1. To what extent did psychological safety impact your previous work experience?

In my previous work in the MIlitary, was something that I had to learn to watch what I say or do. It was very unsafe in the sense that I could lose my rank or not speak up about certain things that would come back and haunt me.  The way you had to communicate, or act in a certain manner so that you aren’t in the spotlight, were a couple of examples of what I’ve experienced.

## 2. How does this article inform your approach to working with others moving forward?

With my past experiences in the Navy and  Army along with this article, I can honestly say that I won’t tolerate anything that makes me feel unsafe. I believe working in a safe environment,  but I also believe standing up for myself. I’ve matured in through the years to speak up and say something that is not right, even when it is the unfavorable thing to do.
How I explained REST to my brother

## 1. Who is Roy Fielding?

Roy Fielding is a computer scientist who is best known for his work in developing the World Wide Web and for his contributions to the field of software architecture. He played a significant role in creating the Hypertext Transfer Protocol (HTTP) and the Uniform Resource Identifier (URI) standards, which are fundamental to the functioning of the web.
Fielding is particularly recognized for his doctoral dissertation, titled "Architectural Styles and the Design of Network-based Software Architectures," which he completed in 2000 at the University of California, Irvine. In this dissertation, he introduced the Representational State Transfer (REST) architectural style, which has since become widely adopted for designing networked applications and web services.
RESTful architectures emphasize the use of standard protocols and stateless communication between clients and servers, enabling scalability, flexibility, and interoperability across distributed systems. Fielding's work has had a profound influence on the development of the modern web and the design of network-based software systems.
In addition to his academic contributions, Fielding has been involved in various software development projects and has held positions at organizations such as the Apache Software Foundation and Adobe Systems. He continues to be a respected figure in the fields of computer science and software architecture.

## 2. Why don’t the techniques that we use in this class work well when we need to be able to talk to all of the machines in the world?

It seems like you're referring to a computer science or networking class where certain techniques or protocols are taught for communication between machines. While these techniques may work well within a controlled environment or a specific network, they might not be suitable for communicating with all machines worldwide due to several reasons:

1. **Scalability:** Techniques taught in a class may not scale well to the size and complexity of the entire internet. The number of devices connected to the internet is vast and constantly growing. Techniques that work for small-scale networks may become inefficient or impractical when dealing with such a large number of devices.
2. **Interoperability:** The internet is a heterogeneous network comprising various devices, operating systems, and protocols. Not all devices and systems may support the same communication protocols or standards taught in a class. Achieving interoperability across such diverse environments requires more flexible and adaptable communication techniques.
3. **Security:** Communication over the internet needs to be secure to protect data and privacy. Techniques taught in a class may not inherently provide the level of security required for global communication. Additional measures such as encryption, authentication, and secure protocols are necessary to ensure secure communication over the internet.
4. **Reliability:** The internet operates under real-world conditions where network connectivity can be unreliable or intermittent. Techniques taught in a class may not adequately address issues such as packet loss, latency, and network congestion that can affect communication on a global scale.
5. **Standardization:** For communication to be effective on a global scale, it often requires adherence to international standards and protocols. While certain techniques taught in a class may be based on standard protocols, the internet's global nature demands strict adherence to these standards to ensure interoperability and compatibility across different networks and devices.
In summary, while techniques taught in a class may serve as foundational knowledge for understanding networking principles, achieving effective communication with all machines on the internet requires more advanced and specialized techniques that address scalability, interoperability, security, reliability, and adherence to international standards.

## 3. What is the HTTP protocol that Fielding and his friends created?

Roy Fielding, along with his colleagues, played a significant role in developing the Hypertext Transfer Protocol (HTTP), which is a fundamental protocol of the World Wide Web. HTTP is an application layer protocol that governs how web browsers and web servers communicate with each other over the internet.
HTTP enables the transfer of various types of data, including text, images, videos, and other resources, between clients (such as web browsers) and servers. It operates on a request-response model, where a client sends an HTTP request to a server to retrieve or manipulate resources, and the server responds with the requested information or indicates the outcome of the request.
Fielding's contributions to HTTP, along with others involved in its development, have been instrumental in shaping the architecture of the web and enabling the exchange of information across the internet. Additionally, Fielding's doctoral dissertation introduced the Representational State Transfer (REST) architectural style, which has since become closely associated with HTTP and has influenced the design of web services and APIs.

## 4. What does a GET do?

In the context of the Hypertext Transfer Protocol (HTTP), the GET method is one of the most commonly used HTTP request methods. It is used by a client (such as a web browser) to request data from a specified resource (such as a web server). When a client sends a GET request to a server, it asks the server to return a representation of the specified resource.
Here's a simplified breakdown of how a GET request works:

1. **Client sends a GET request:** The client (e.g., a web browser) sends a GET request to a specific URL (Uniform Resource Locator) or endpoint on a server. This request typically includes the URL of the resource being requested and may include additional headers for specifying parameters or options.
2. **Server processes the request:** The server receives the GET request from the client and processes it. It locates the requested resource based on the URL provided in the request.

3. **Server sends a response:** After locating the requested resource, the server generates an HTTP response containing the requested data or information. This response includes a status code (usually 200 OK for a successful request) and the requested resource's content.
4. **Client receives the response:** The client receives the HTTP response from the server. If the request was successful, the client can then parse the response and display the requested resource to the user (e.g., render a web page in the browser).
In summary, the GET method in HTTP is used for retrieving data from a server. It is a safe and idempotent operation, meaning it should not have any side effects on the server and can be repeated multiple times with the same result. GET requests are commonly used for fetching web pages, images, documents, or any other resources available on the web.

## 5. What does a POST do?

In the context of the Hypertext Transfer Protocol (HTTP), the POST method is another commonly used HTTP request method. It is used by a client (such as a web browser) to submit data to be processed to a specified resource on a server. Unlike the GET method, which is primarily used for retrieving data, the POST method is used for sending data to the server to create or update a resource.
Here's a simplified breakdown of how a POST request works:

1. **Client sends a POST request:** The client sends a POST request to a specific URL (Uniform Resource Locator) or endpoint on a server. This request includes the data to be submitted, typically in the form of key-value pairs or a structured data format such as JSON (JavaScript Object Notation) or XML (eXtensible Markup Language). This data can include form inputs, file uploads, or any other type of data that needs to be processed by the server.
2. **Server processes the request:** The server receives the POST request from the client and processes the submitted data. The server may perform various actions based on the data received, such as storing it in a database, updating existing records, or performing other business logic.
3. **Server sends a response:** After processing the data, the server generates an HTTP response containing the result of the operation. This response typically includes a status code indicating the outcome of the request (such as 200 OK for a successful request) and may include additional data or information.
4. **Client receives the response:** The client receives the HTTP response from the server. Depending on the response, the client may take further action, such as displaying a confirmation message to the user or redirecting to another page.
In summary, the POST method in HTTP is used for submitting data to a server for processing. It is commonly used for actions such as submitting forms, uploading files, or making requests that result in creating or updating resources on the server. Unlike the GET method, which is idempotent and safe, POST requests can have side effects on the server and are not guaranteed to be idempotent.

## 6. What does PUT do?

The PUT method in the context of HTTP (Hypertext Transfer Protocol) is one of the standard request methods used to send data to a server to create or update a resource at a specific URL.
Here's what PUT does:
1.**Update or Create Resource:** PUT is used to update or create a resource on the server at a specified URL. If the resource already exists at the given URL, PUT will update it with the new data provided in the request. If the resource does not exist, PUT will create a new resource using the provided data.
2.**Idempotent Operation:** PUT is considered idempotent, which means that making the same request multiple times will have the same effect as making it once. If a client sends a PUT request to update a resource and then sends the same request again, it will result in the same resource state as if it were only sent once. This property is useful for ensuring consistency and reliability in distributed systems.
3. **Data Transmission:** The data to be updated or created is typically included in the body of the PUT request. This data can be in various formats, such as JSON (JavaScript Object Notation), XML (eXtensible Markup Language), or plain text, depending on the application's requirements.
4. **Response:** After processing the PUT request, the server will send an HTTP response to the client to indicate the outcome of the operation. This response usually includes a status code (e.g., 200 OK for a successful update, 201 Created for successful creation) and may include additional information about the updated or created resource.
In summary, the PUT method in HTTP is used to update or create resources on the server, and it's an idempotent operation, making it suitable for scenarios where consistency and reliability are essential.

## 7. What does PATCH do?

The PATCH method in the context of HTTP (Hypertext Transfer Protocol) is another standard request method used to apply partial modifications to a resource. It is typically used when a client wants to update only a portion of a resource rather than replacing it entirely, as with the PUT method. PATCH is particularly useful for making minor updates or modifications to resources without having to send the entire representation of the resource in the request.
Here's what PATCH does:
1.**Partial Modification:** PATCH is used to apply partial modifications to a resource on the server. Unlike PUT, which requires sending the entire representation of the resource with the update, PATCH allows clients to specify only the changes they want to apply to the resource.
2.**Idempotent Operation:** Like PUT, PATCH is also considered idempotent, meaning that making the same request multiple times will have the same effect as making it once. This property ensures that repeated PATCH requests do not produce unintended side effects or alter the resource state differently each time.
3.**Data Transmission:** The data to be applied as modifications is typically included in the body of the PATCH request. This data can be in various formats, such as JSON (JavaScript Object Notation), XML (eXtensible Markup Language), or plain text, depending on the application's requirements.
4.**Response:** After processing the PATCH request, the server will send an HTTP response to the client to indicate the outcome of the operation. This response usually includes a status code (e.g., 200 OK for a successful update) and may include additional information about the modified resource.
In summary, the PATCH method in HTTP is used to apply partial modifications to resources on the server. It's particularly useful for scenarios where only specific parts of a resource need to be updated, providing a more efficient and flexible approach compared to replacing the entire resource with the PUT method.

API Keys
Request a personal API key from the following APIs. You should receive these in your email within a few hours, often within minutes. Please request these keys prior to lecture to allow adequate time because you will need them in order to complete your lab assignment. Note: do not post your API keys in the Canvas discussion or on GitHub. Save them in a secure place.
Geocoding API

## 1. Did you get your API key?

Yes!

Weather Bit API

## 1. Did you get your API key?

Yes!

Yelp API Docs

## 1. Did you get your API key?

Yes!

The Movie DB API Docs

## 1. Did you get your API key?

Yes!

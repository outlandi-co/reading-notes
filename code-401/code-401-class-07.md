# Reading: Bearer Authorization

Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.
Review the Submission Instructions for guidance on completing and submitting this assignment.
Reading
Intro to JWT
What is a JSON Web Token (JWT)?
A JSON Web Token (JWT) is a compact, URL-safe means of representing claims to be transferred between two parties. The claims in a JWT are encoded as a JSON object that is used as the payload of a JSON Web Signature (JWS) structure or as the plaintext of a JSON Web Encryption (JWE) structure, enabling the claims to be digitally signed or integrity protected with a Message Authentication Code (MAC) and/or encrypted.
JWTs are commonly used for authentication and authorization in web applications and APIs. They are often used as a secure way to transmit information between parties in a compact and self-contained manner. A JWT typically consists of three parts separated by dots: the header, the payload, and the signature. These parts are base64url encoded and concatenated to form the token.
The header typically contains metadata about the token such as the type of token and the cryptographic algorithms used to secure it. The payload contains the claims, which are statements about an entity (typically the user) and additional data. The signature is used to verify that the sender of the JWT is who it says it is and to ensure that the message wasn't changed along the way.
JWTs are often used in authentication systems where a user logs in and receives a JWT token, which is then included in subsequent requests to access protected resources. The server can then validate the JWT and extract the claims to determine if the user is authorized to access the requested resource.
When should we use JSON Web Tokens?
JSON Web Tokens (JWTs) are commonly used in various scenarios, particularly in web applications and APIs. Here are some situations where JWTs are often employed:

1.**Authentication**: JWTs are frequently used for user authentication. When a user logs in, the server generates a JWT containing information about the user (claims), such as their user ID or role. This token is then sent back to the client, typically stored in local storage or a cookie. Subsequent requests from the client include the JWT, allowing the server to verify the user's identity without the need to look up session state on the server. This stateless nature makes JWTs suitable for distributed systems.
2.**Authorization**: JWTs can also be used for authorization. The claims within the JWT can include information about the user's permissions or roles. When a user attempts to access a protected resource, the server can examine the JWT to determine if the user has the necessary permissions.
3.**Single Sign-On (SSO)**: JWTs are often used in SSO systems, where a user logs in once and gains access to multiple applications without needing to log in again. After authentication, the user receives a JWT, which can be used to access other services within the same SSO ecosystem. This simplifies the authentication process and enhances user experience.
4.**Information Exchange**: JWTs can be used to securely exchange information between parties. Since JWTs can be digitally signed, the receiving party can verify the integrity and authenticity of the information contained within the token. This makes JWTs suitable for transmitting claims in a secure and tamper-proof manner.
5.**Microservices**: In a microservices architecture, JWTs can be used to secure communication between services. Each service can verify the JWT to ensure that the request comes from an authenticated and authorized source. This simplifies the implementation of security across distributed systems.
Overall, JWTs are a versatile tool for securing and transmitting information in web applications and APIs, particularly in scenarios where stateless authentication and authorization are desired. However, it's important to consider factors such as token expiration, token validation, and security best practices when using JWTs in your applications.

Claims are expected in which structural component of a JWT?
Claims are expected in the payload of a JSON Web Token (JWT).
The payload of a JWT contains the actual data being transmitted, which typically consists of a set of claims. Claims are statements about an entity (typically the user) and additional data. These claims are represented as a JSON object within the payload of the JWT.
There are three types of claims:

1.**Reserved Claims**: These are predefined claims recommended by the JWT specification, such as "iss" (issuer), "sub" (subject), "aud" (audience), "exp" (expiration time), and "iat" (issued at time).
2.**Public Claims**: These are custom claims defined by the parties involved in the JWT communication. They are typically used to convey information specific to the application or use case.
3.**Private Claims**: These are custom claims agreed upon by the parties involved in the JWT communication but are not registered or standardized. They are meant for private use between the parties.
Claims provide useful information about the entity (e.g., user) and context of the JWT, such as user ID, roles, permissions, and additional metadata. These claims can be used by the recipient of the JWT to make decisions regarding authentication, authorization, and other business logic.

Are JWTs Secure?
If I get a JWT and I can decode the payload, how can we call that secure?
Decoding the payload of a JWT does not compromise its security, as the payload is designed to be readable by anyone who possesses the token. The security of a JWT primarily relies on two aspects:

1.**Token Integrity**: JWTs are often digitally signed using cryptographic algorithms, such as HMAC or RSA, to ensure their integrity. The signature, which is included as part of the token, is calculated based on the header and payload of the JWT, along with a secret key known only to the issuer. Verifying the signature allows the recipient to confirm that the token has not been tampered with since it was issued. If the signature verification fails, the recipient knows that the token has been altered and can reject it.
2.**Sensitive Data**: While the payload of a JWT is not encrypted and can be decoded by anyone, it's essential to avoid including sensitive information directly in the payload. Instead, sensitive data should be stored on the server-side and referenced by an identifier (e.g., a user ID) included in the JWT payload. This approach ensures that even if a JWT is decoded by an unauthorized party, they cannot access sensitive information directly from the token.
In summary, JWTs are considered secure because:

- They are digitally signed, allowing recipients to verify their integrity.
- They do not expose sensitive information directly in the payload, mitigating the risk of data exposure even if the token is decoded.
However, it's crucial to handle JWTs securely, including protecting the secret keys used for signing and implementing appropriate measures to prevent token misuse, such as enforcing token expiration and revocation mechanisms. Additionally, JWTs alone do not provide confidentiality, so if confidentiality of the payload is required, additional encryption mechanisms should be employed.

If sending a JWT, what must sender and receiver both know? Hint, it’s appended in the signature.
In the context of sending a JWT, the sender and receiver both must know a shared secret key. This shared secret key is used to compute or verify the signature appended to the JWT.
When the sender creates the JWT, it calculates the signature using the shared secret key and appends it to the JWT. When the receiver receives the JWT, it also calculates the signature using the shared secret key. If the calculated signature matches the signature appended to the JWT, the receiver can be confident that the JWT has not been tampered with during transit.
This shared secret key is critical for ensuring the integrity and authenticity of the JWT. It should be kept confidential and known only to the parties involved in JWT creation and verification.

Explain how concatenated content and secret can be sent and received securely to a non-technical recruiter.
When explaining how concatenated content and a secret can be sent and received securely to a non-technical recruiter, you can use an analogy or a simplified explanation to make it understandable:
Imagine you have a treasure chest (the concatenated content) that you want to send to your friend across a dangerous ocean. However, you want to make sure the chest arrives safely and that nobody tampers with it along the way. So, you decide to lock the chest with a special key (the secret).
Here's how you explain it:

1.**Creating the Treasure Chest (Concatenated Content)**: You gather all the valuable items you want to send to your friend and put them in a chest. This chest represents the information you want to send securely.
2.**Locking the Treasure Chest (Using a Secret)**: Before sending the chest, you lock it with a special key. This key is known only to you and your friend. It's like a secret code that only the two of you understand.
3.**Sending the Locked Treasure Chest (Sending the JWT)**: You send the locked chest across the ocean to your friend. Even if someone tries to open the chest during the journey, they won't be able to because it's securely locked with the special key.
4.**Receiving the Locked Treasure Chest (Receiving the JWT)**: Your friend receives the locked chest. They know the special key, so they use it to unlock the chest and access the valuable items inside.
In this analogy:

- The treasure chest represents the concatenated content (the payload) of the JWT.
- The special key represents the secret key used to create the signature appended to the JWT.
- Sending and receiving the locked treasure chest represents the process of transmitting and receiving the JWT securely.
By using this analogy, you can help the non-technical recruiter understand the concept of sending and receiving information securely using concatenated content and a secret key, without delving into technical details.

Videos
JWTs Explained
Why use JWT?
There are several reasons why JSON Web Tokens (JWTs) are widely used in web development and API authentication:

1.**Statelessness**: JWTs are stateless, meaning the server does not need to store session state. This reduces server overhead and simplifies scalability, as each request contains all the necessary information for authentication and authorization.
2.**Compactness and Efficiency**: JWTs are compact, which makes them efficient for transmission over the network. They are typically smaller in size compared to traditional session-based authentication mechanisms, such as cookies, resulting in reduced bandwidth usage and faster data transmission.
3.**Cross-Domain Compatibility**: JWTs can be easily transmitted across different domains or systems, making them suitable for use in distributed architectures, microservices, and cross-domain authentication scenarios.
4.**Security**: JWTs can be digitally signed using cryptographic algorithms, providing integrity and authenticity of the transmitted data. This ensures that the token has not been tampered with or altered during transmission.
5.**Flexibility and Extensibility**: JWTs support the inclusion of custom claims, allowing developers to include additional metadata or user-specific information in the token payload. This flexibility enables JWTs to be adapted to various use cases and application requirements.
6.**Caching**: Since JWTs contain all the necessary information for authentication and authorization, they can be easily cached on the client side, improving performance and reducing the number of database lookups or server calls required for authentication.
7.**Standardization**: JWTs are based on open standards (RFC 7519), making them widely supported and interoperable across different programming languages, platforms, and frameworks. This standardization promotes consistency and compatibility in authentication implementations.
Overall, JWTs provide a lightweight, secure, and flexible solution for authentication and authorization in modern web applications and APIs, offering benefits such as statelessness, compactness, security, and interoperability.
JWT is Compact and self-contained. Describe how this is useful to a non-technical friend.
Imagine you're sending a secret message to your friend, but you want to make sure it's safe and easy to handle. Using a compact and self-contained format, like a small box, can help with that.
Here's how you can explain it to your non-technical friend:

1.**Compactness**: Just like a small box, a JWT is very compact. It doesn't take up much space, which makes it easy to send over the internet. This means it's quick to transmit from one place to another, just like sending a small package in the mail. So, instead of sending a big, bulky package (like some other authentication methods), you're sending a small, efficient one.
2.**Self-contained**: Inside this small box (the JWT), you can put everything you need. It's like packing all the ingredients for a recipe into a single container. In the case of a JWT, it contains all the information needed for authentication and authorization. This includes details like who you are, what you can do, and when the information expires. So, just like you wouldn't need to go back to the store for missing ingredients if you packed them all together, a JWT has everything it needs in one place.
By using this analogy, your non-technical friend can understand that JWTs are like small, efficient packages containing all the necessary information, making them easy to send and handle securely.
What are the three components (the structure) of a JWT signature?
The JWT signature consists of three components:

1.**Header**: The header typically consists of two parts: the type of token (JWT) and the hashing algorithm being used, such as HMAC SHA256 or RSA. It is JSON-encoded and base64url encoded to form the first part of the signature.
2.**Payload**: The payload contains the claims, which are statements about an entity (typically the user) and additional data. These claims are also JSON-encoded and base64url encoded to form the second part of the signature.
3.**Signature**: The signature is the result of combining the encoded header, encoded payload, and a secret key, and then hashing the combined result using the specified algorithm. This signature ensures the integrity of the token and verifies that it has not been tampered with. The signature is appended to the JWT, forming the third part of the signature.
When put together, these three components create the complete JWT signature, which can be used to verify the authenticity and integrity of the token.

Bookmark and Review
npm jsonwebtoken docs
Reflection
What are your learning goals after reading and reviewing the class README?
As a passionate learner in the realm of web development, I am continually driven by the pursuit of knowledge and the desire to master the intricacies of secure authentication mechanisms. With a deep understanding of the significance of web security, I am committed to refining my skills in implementing robust Bearer Token Authentication systems and leveraging the power of JSON Web Tokens (JWT) to ensure data integrity and user privacy. Through hands-on experience and dedicated study, I strive to contribute meaningfully to the advancement of secure web technologies while embracing the challenges and opportunities that lie ahead.

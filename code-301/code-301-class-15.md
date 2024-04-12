# Reading-Notes 15

Readings: Authentication

Below you will find some reading material, code samples, and some additional resources that support the topic for this class and the upcoming lecture.
Review the Submission Instructions for guidance on completing and submitting this assignment.
Reading

## 1. What is OAuth?

OAuth (Open Authorization) is an open standard for authorization that allows users to grant third-party websites or applications access to their resources without sharing their credentials (such as usernames and passwords). It provides a secure way for users to authorize external services to access their data stored on another service without revealing their passwords.
In simpler terms, OAuth enables users to grant limited access to their resources on one website (the service provider) to another website or application (the client) without sharing their credentials. This is commonly seen when you log in to a website using your Google, Facebook, or Twitter account. Instead of creating a new account on the website, you can authorize the website to access certain information from your Google, Facebook, or Twitter account.
OAuth operates through a series of authorization steps, including authorization request, granting permission, token request, and accessing resources. It ensures security by providing access tokens that can be used by the client to access the user's resources on the service provider's server, without exposing the user's credentials.

## 2. Give an example of what using OAuth would look like

1. You open the mobile app and choose the option to log in with your Google account.
2. The app redirects you to Google's authentication page, where you're asked to enter your Google username and password.
3. After entering your credentials, Google prompts you with a message asking if you authorize the app to access certain information from your Google account, such as your name, email address, or profile picture.
4. Once you grant permission, Google generates an access token and sends it back to the app.
5. The app receives the access token and uses it to make requests to Google's API on your behalf, accessing the requested information.
6. You are now logged in to the app and can start using it, with the app having access to the authorized information from your Google account.
In this example, OAuth facilitates the authentication process between the app and Google without the app ever knowing your Google password. Instead, it relies on Google's authentication system to verify your identity and grant access to the app.

## 3. How does OAuth work? What are the steps that it takes to authenticate the user?

OAuth works through a series of steps to authenticate the user and authorize access to their resources. Here's a general overview of the OAuth process:

1. **Authorization Request**: The client application initiates the OAuth process by requesting authorization from the user. This typically involves redirecting the user to the authorization server (the service provider) with a specific authorization request.
2. **User Authentication**: The user is prompted to authenticate themselves with the authorization server. This may involve logging in with their username and password or using other authentication methods such as biometric authentication or single sign-on (SSO).
3. **Authorization Grant**: Once authenticated, the user is presented with a consent screen where they can review the permissions requested by the client application. The user can choose to grant or deny these permissions.
4. **Authorization Response**: If the user grants permission, the authorization server issues an authorization code or access token to the client application. This authorization code is typically sent back to the client application via a callback URL.
5. **Token Request**: The client application exchanges the authorization code for an access token by sending a token request to the authorization server. This token request includes the authorization code, client credentials (such as client ID and client secret), and other required parameters.
6. **Access Token**: Upon receiving the token request, the authorization server verifies the authorization code and issues an access token to the client application if everything is valid. This access token represents the user's authorization to access their resources.
7. **Resource Access**: The client application can now use the access token to make authorized requests to the resource server (the server hosting the user's resources). The resource server validates the access token and grants access to the requested resources if the token is valid.
8. **Token Expiration and Refresh**: Access tokens typically have a limited lifespan (expiration time). If the access token expires, the client application can use a refresh token (if provided) to obtain a new access token without requiring the user to re-authenticate. This helps maintain security while providing a seamless user experience.

Overall, OAuth enables secure, delegated access to resources by allowing client applications to obtain access tokens on behalf of users, without exposing the user's credentials to the client application. It provides a standardized framework for authentication and authorization in distributed systems.

## 4. What is OpenID?

OpenID is an open standard and decentralized authentication protocol that allows users to be authenticated by certain cooperating sites (known as relying parties) using a third-party service, eliminating the need for webmasters to provide their own ad hoc login systems, and allowing users to log in to multiple unrelated websites without having to have a separate identity and password for each.
In simpler terms, OpenID allows users to use a single set of credentials (such as a username and password) to log in to multiple websites or services that support OpenID authentication. This means that users can create and manage one account with an OpenID provider (such as Google, Yahoo, or other identity providers) and use that account to log in to various websites and services that accept OpenID credentials.
OpenID operates on the principle of decentralized authentication, where identity providers (OpenID providers) authenticate users and provide them with an identity URL (OpenID URL). When a user wants to log in to a website or service that supports OpenID, they enter their OpenID URL instead of a username and password. The relying party then redirects the user to their OpenID provider for authentication. Once authenticated, the OpenID provider sends back a response to the relying party, confirming the user's identity. This allows the user to access the relying party's website or service without having to create a new account or share additional credentials.
Overall, OpenID aims to simplify the login process for users by enabling them to use a single set of credentials across multiple websites and services, while also providing a more secure and privacy-friendly authentication mechanism compared to traditional username and password authentication.

Authorization and Authentication flows

## 1. What is the difference between authorization and authentication?

Authorization and authentication are both important aspects of security protocols, but they serve different purposes:

1. **Authentication**:
   - Authentication is the process of verifying the identity of a user or system, ensuring that they are who they claim to be.
   - It involves presenting credentials, such as a username and password, biometric data, security tokens, or digital certificates, to a system or service.
   - Authentication typically occurs at the beginning of a session or interaction, allowing the system to determine whether the user or entity is authorized to access the requested resources.
   - Example: When you log in to a website using your username and password, the website authenticates you by verifying that the credentials you provided match the stored credentials associated with your account.
2. **Authorization**:
   - Authorization is the process of determining whether a user or system has the necessary permissions and privileges to access a particular resource or perform a specific action within a system or application.
   - It involves granting or denying access based on the authenticated user's identity and their associated permissions.
   - Authorization typically occurs after authentication, as the system needs to know the user's identity before making decisions about what resources they can access.
   - Example: After you successfully log in to a website, the website checks your user account's permissions to determine whether you have the authorization to view certain pages, edit specific content, or perform other actions.

In summary, authentication verifies the identity of a user or system, while authorization determines what actions or resources the authenticated user is allowed to access. Authentication precedes authorization in the security process, as access control decisions rely on knowing the user's identity first.

## 2. What is Authorization Code Flow?

The Authorization Code Flow is an OAuth 2.0 grant type used for obtaining an access token on behalf of a user. It is commonly used in scenarios where the client application operates a web server and can securely store client secrets.
Here's how the Authorization Code Flow works:

1. **Authorization Request**: The client application initiates the flow by redirecting the user to the authorization server's authorization endpoint. The request includes parameters such as client ID, redirect URI, scope, and optionally state.
2. **User Authentication**: The user is prompted to log in to the authorization server and authorize the client application to access their resources. This step typically involves the user entering their credentials and granting consent for the requested permissions.
3. **Authorization Grant**: Upon successful authentication and authorization, the authorization server redirects the user back to the client application's redirect URI with an authorization code appended to the URL as a query parameter. This authorization code serves as a temporary authorization grant.
4. **Token Request**: The client application exchanges the authorization code for an access token by making a request to the authorization server's token endpoint. The request includes the authorization code, client ID, client secret, redirect URI, and grant type (authorization code).
5. **Access Token**: The authorization server verifies the authorization code, client credentials, and other parameters and issues an access token to the client application if everything is valid. The access token represents the client application's authorization to access the user's resources on behalf of the user.
6. **Resource Access**: The client application can now use the access token to make authorized requests to the resource server (the server hosting the user's resources). The resource server validates the access token and grants access to the requested resources if the token is valid.

The Authorization Code Flow provides several security benefits, including the separation of client credentials from the access token and the ability to authenticate the client application securely using its client secret. It is well-suited for web applications where the client secret can be securely stored on the server-side.

## 3. What is Authorization Code Flow with Proof Key for Code Exchange (PKCE)?

The Authorization Code Flow with Proof Key for Code Exchange (PKCE) is an enhanced version of the standard Authorization Code Flow in OAuth 2.0. It is designed to provide additional security when mobile or native applications are involved, where the client secret cannot be reliably stored.
Here's how the Authorization Code Flow with PKCE works:

1. **Initial Request**: The client application generates a unique code verifier and a code challenge. The code verifier is a random string of characters, and the code challenge is derived from the code verifier using a cryptographic hash function, typically SHA-256.
2. **Authorization Request**: The client application initiates the flow by redirecting the user to the authorization server's authorization endpoint. The request includes parameters such as client ID, redirect URI, scope, and the code challenge method along with the generated code challenge.
3. **User Authentication**: The user is prompted to log in to the authorization server and authorize the client application to access their resources. This step is similar to the standard Authorization Code Flow.
4. **Authorization Grant**: Upon successful authentication and authorization, the authorization server redirects the user back to the client application's redirect URI with an authorization code appended to the URL as a query parameter.
5. **Token Request**: The client application exchanges the authorization code for an access token by making a request to the authorization server's token endpoint. Additionally, the client application includes the original code verifier used to generate the code challenge.
6. **Access Token**: The authorization server verifies the authorization code, client credentials, and the code verifier. If everything is valid, the authorization server issues an access token to the client application. The access token represents the client application's authorization to access the user's resources.

The use of PKCE mitigates the risk of authorization code interception and replay attacks, which are more prevalent in mobile and native applications where the client secret cannot be reliably stored. By dynamically generating and verifying a code challenge, PKCE ensures that only the client application that initiated the authorization request can exchange the authorization code for an access token.

## 4. What is Implicit Flow with Form Post?

The Implicit Flow with Form Post is an OAuth 2.0 flow primarily designed for single-page web applications (SPAs) that run entirely in the browser and cannot securely store client secrets. It is an alternative to the standard Authorization Code Flow, which requires a client secret to be securely stored on the client side.
Here's how the Implicit Flow with Form Post works:

1. **Authorization Request**: The client application initiates the flow by redirecting the user to the authorization server's authorization endpoint. The request includes parameters such as client ID, redirect URI, response type set to "token", and scope.
2. **User Authentication**: The user is prompted to log in to the authorization server and authorize the client application to access their resources. This step is similar to other OAuth 2.0 flows.
3. **Authorization Response**: Upon successful authentication and authorization, the authorization server redirects the user back to the client application's redirect URI with an access token appended to the URL as a fragment identifier (hash). Additionally, the response may include other parameters such as token type, expiration time, and scope.
4. **Form Post**: Instead of exposing the access token directly in the URL (which could be susceptible to certain security risks, such as token leakage through browser history or referrer headers), the client application uses JavaScript to extract the access token from the URL fragment and then submits it to the server using an HTTP POST request within a hidden form. This ensures that the access token is not exposed to potential attackers.
5. **Token Validation**: The server receives the access token via the POST request and validates it with the authorization server to ensure its authenticity and integrity. If the token is valid, the server can then use it to access protected resources on behalf of the user.

It's important to note that while the Implicit Flow with Form Post eliminates the need for storing client secrets on the client side, it does introduce certain security considerations, such as the risk of cross-site scripting (XSS) attacks if proper precautions are not taken to securely handle access tokens within the client-side JavaScript code. Additionally, since access tokens are transmitted via URL fragments, they may still be vulnerable to certain attacks, such as token leakage via browser history or referrer headers.

## 5. What is Client Credentials Flow?

The Client Credentials Flow is an OAuth 2.0 grant type that allows a client application to request an access token using its own credentials (client ID and client secret), rather than on behalf of a specific user. This flow is typically used when the client application needs to access its own resources, rather than resources belonging to a user.
Here's how the Client Credentials Flow works:

1. **Client Authentication**: The client application authenticates itself to the authorization server by providing its client ID and client secret. These credentials are typically obtained when the client application is registered with the authorization server.
2. **Token Request**: After successful authentication, the client application sends a token request to the authorization server's token endpoint. The request includes the client credentials, as well as the grant type set to "client_credentials".
3. **Access Token**: The authorization server verifies the client credentials and issues an access token to the client application if everything is valid. This access token represents the client application's authorization to access the requested resources.
4. **Resource Access**: The client application can now use the access token to make authorized requests to the resource server (the server hosting the client's resources). The resource server validates the access token and grants access to the requested resources if the token is valid.

The Client Credentials Flow is commonly used in scenarios where the client application needs to access resources that are not associated with a specific user, such as accessing APIs for administrative purposes or performing system-to-system communication. It does not involve user authentication, as the client application is acting on its own behalf rather than on behalf of a user.

## 6. What is Device Authorization Flow?

The Device Authorization Flow, also known as the Device Flow or OAuth 2.0 Device Authorization Grant, is an OAuth 2.0 flow designed for devices with limited input capabilities, such as smart TVs, media players, and Internet of Things (IoT) devices. It allows such devices to obtain user authorization to access resources on behalf of the user without requiring a full web browser or direct user interaction.
Here's how the Device Authorization Flow works:

1. **Device Request**: The device initiates the flow by making a request to the authorization server's device authorization endpoint. The request typically includes the client ID identifying the device, the scope of the requested access, and any other required parameters.
2. **User Code Display**: The authorization server responds with a unique user code and a verification URL. The user code is typically a short alphanumeric code that the user needs to enter on a separate device with a web browser.
3. **User Authorization**: The user navigates to the verification URL on their separate device (such as a smartphone or computer) and enters the provided user code. This directs the user to the authorization server's authorization page, where they can log in and authorize the device to access their resources.
4. **Token Request**: While the user is authorizing the device, the device repeatedly polls the authorization server's token endpoint using the device code provided earlier. It continues to do so until the user has successfully authorized the device or the authorization expires.
5. **Access Token**: Once the user has authorized the device, the authorization server issues an access token to the device. The device can then use this access token to make authorized requests to the resource server on behalf of the user.

The Device Authorization Flow is particularly useful for devices with limited input capabilities or no direct user interface, as it allows them to obtain user authorization without requiring a full web browser or keyboard input. It provides a secure and user-friendly way for users to authorize devices to access their resources.

## 7. What is Resource Owner Password Flow?

The Resource Owner Password Credentials (ROPC) Flow, also known as the Resource Owner Password Flow or Resource Owner Password Grant, is an OAuth 2.0 flow that allows an application to exchange a user's username and password for an access token directly.
In the ROPC flow, the client application collects the user's username and password and sends them directly to the authorization server's token endpoint to obtain an access token. This flow is typically used when the client application is highly trusted, such as in legacy applications or when other OAuth flows are not suitable.
Here's how the Resource Owner Password Credentials Flow works:

1. **User Credentials**: The user provides their username and password directly to the client application, rather than being redirected to the authorization server for authentication.
2. **Token Request**: The client application sends a token request to the authorization server's token endpoint. The request includes the user's username and password, along with the client credentials (client ID and client secret) and the grant type set to "password".
3. **Access Token**: The authorization server validates the user's credentials and issues an access token to the client application if everything is valid. This access token represents the user's authorization to access protected resources.
4. **Resource Access**: The client application can now use the access token to make authorized requests to the resource server (the server hosting the user's resources). The resource server validates the access token and grants access to the requested resources if the token is valid.
It's important to note that the Resource Owner Password Credentials Flow bypasses some of the security benefits provided by other OAuth 2.0 flows, such as the separation of concerns between the client application and the authorization server. Additionally, since the user's username and password are transmitted directly to the client application, it's crucial to ensure that the client application is secure and trusted to handle sensitive user credentials. This flow should be used judiciously and only when other OAuth flows are not suitable or feasible.

Videos
Bookmark and Review
Auth0 for single page apps

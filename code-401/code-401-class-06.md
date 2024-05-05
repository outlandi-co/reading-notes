# Readings: Authentication

Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.
Review the Submission Instructions for guidance on completing and submitting this assignment.
Readings
Securing Passwords
Explain to a non-technical friend how you would safely hash and store a password.
Imagine your password is like a secret recipe that only you and the website know. Now, instead of storing the recipe itself, we're going to do something special with it. We're going to put it through a magic blender called a "hash function." This blender takes your recipe and turns it into a unique, scrambled mess.
Once it's all scrambled up, we'll put it in a super secure vault, which is like the website's database. So, even if someone sneaks into the vault, all they'll find is this scrambled mess, not your original recipe. But here's the cool part: whenever you come back to the website and want to log in, we'll just put your recipe through the blender again and check if it matches the scrambled mess we stored before. If it does, you're in!
This way, even if someone gets into the vault, they won't be able to figure out your original recipe because it's all mixed up and hidden away. It's like turning your password into a secret code that only the website knows how to decode. And that's how we keep your password safe and sound.

What is Bcrypt?
Bcrypt is like a super-powered blender specifically designed for scrambling passwords. When we want to store a password securely, we take it and pass it through Bcrypt. What comes out is a scrambled version of the password that's really hard to unscramble. This process is important for keeping your password safe in case anyone tries to break into the website's vault where passwords are stored. Bcrypt makes it much more difficult for them to figure out your original password, which helps keep your account safe and secure.
Why might you use something like Bcrypt?
We use Bcrypt or similar hashing algorithms because they offer a high level of security for storing passwords. Here's why:

1. **Resistance to Brute Force Attacks**: Bcrypt is designed to be slow, deliberately making it harder for attackers to guess passwords through brute force methods where they try every possible combination.
2. **Protection Against Rainbow Table Attacks**: Bcrypt adds a unique "salt" to each password before hashing it. This means even if two users have the same password, their hashed passwords will look completely different. It prevents attackers from using precomputed tables of hashed passwords, known as rainbow tables, to quickly reverse-engineer passwords.

3. **Adaptability to Hardware Advances**: Bcrypt is designed to be computationally intensive, which means it can adapt to advances in hardware technology. As computers become more powerful, Bcrypt can increase the computational effort required to hash passwords, maintaining its effectiveness against attacks.
4. **Scalability and Longevity**: Bcrypt has been widely adopted and vetted by security experts over time, making it a trusted choice for password hashing. Its proven track record and continued use in the industry speak to its effectiveness and reliability.
Overall, using Bcrypt enhances the security of user passwords, helping to protect sensitive information and maintain user trust in the integrity of the system.

Basic Auth
What is Basic Authentication?
Basic Authentication is a simple method used by web servers to control access to resources. When you try to access a protected page or resource on a website, the server challenges your browser to provide credentials, typically a username and password.

1. The server sends a response with a status code of 401 (Unauthorized) and includes a header called "WWW-Authenticate" indicating that it requires authentication.
2. Your browser prompts you to enter your username and password.
3. Your browser then constructs a special header called "Authorization" that contains your username and password, encoded in a specific format.
4. It sends another request to the server, this time including the "Authorization" header with your credentials.
5. The server verifies your credentials. If they're correct, it grants you access to the requested resource. If not, it returns another 401 response, and the process repeats until the correct credentials are provided or access is denied.
Basic Authentication is straightforward to implement and can be used with any web browser or HTTP client. However, it has limitations in terms of security, as the username and password are sent over the network in base64-encoded form, which can be intercepted and decoded by an attacker. Therefore, it's typically used in conjunction with HTTPS (HTTP Secure) to encrypt the communication between the client and server, reducing the risk of eavesdropping.

What properties are necessary in the header of a Basic Auth request?
In a Basic Authentication request, the header must include the following properties:

Authorization: Basic QWxhZGRpbjpvcGVuIHNlc2FtZQ==
In this example, "QWxhZGRpbjpvcGVuIHNlc2FtZQ==" is the base64-encoded string of "username:password".
The "username:password" part is the concatenation of the username and password separated by a colon ":".
Remember that this encoding does not provide encryption or hashing; it's just a way of representing the credentials in a format that can be sent over the network. It's important to use HTTPS to ensure the security of the transmitted data.

How are username:password in Basic Auth encoded?
In Basic Authentication, the username and password are combined into a single string in the format "username:password". Then, this string is encoded using Base64 encoding. Base64 encoding is a method of converting binary data into ASCII characters, making it suitable for transmitting data over protocols that require plain text, like HTTP.
Here's a step-by-step breakdown of how the username and password are encoded:

1. Concatenate the username and password with a colon ":" separating them, like this: "username:password".
2. Encode the resulting string using Base64 encoding.
3. The encoded string is then included in the Authorization header of the HTTP request.
For example, if the username is "user123" and the password is "password456", the encoded string would be:
user123:password456   (original string)
dXNlcjEyMzpwYXNzd29yZDQ1Ng==   (Base64 encoded string)
So, in the Authorization header of the HTTP request, it would look like this:
Authorization: Basic dXNlcjEyMzpwYXNzd29yZDQ1Ng==
It's important to note that Base64 encoding is not a form of encryption or hashing. It's simply a way of representing data so that it can be transmitted over the network in a text format. Therefore, it's crucial to use HTTPS (HTTP Secure) to ensure the security of the transmitted credentials.
OWASP auth cheatsheet
Define the authentication process to a non-technical recruiter.
Imagine you're throwing a big party, and you want to make sure only the invited guests get in. So, at the entrance, you have a bouncer who checks everyone's names against the guest list.
Now, in the online world, when you visit a website or use an app, there's a similar process called authentication. It's like proving your identity to gain access.
Here's how it works:

1.**You Knock on the Door**: You try to access a website or app by typing in the web address or clicking on a link.
2.**The Website Says, "Who's There?"**: The website then asks you to provide some information to prove you're allowed to enter. This could be a username and password, like a secret handshake to get in.
3.**You Give Your Credentials**: You type in your username (like your name on the guest list) and your password (the secret code only you know).
4.**The Bouncer Checks the List**: The website checks your username and password against its records to see if you're on the list of approved users.
5.**You Get the Green Light or the Red Light**: If your username and password match what the website has on record, you get access! It's like the bouncer saying, "Come on in!" But if they don't match, you might get a message like, "Sorry, you're not on the list," and you won't be able to enter.
That's basically how authentication works online. It's all about making sure you are who you say you are before letting you in.
How should your error messaging respond (both HTTP and HTML)? Why?
Error messaging plays a crucial role in user experience, especially during authentication processes. Here's how error messaging should be handled both in HTTP responses and HTML pages, along with the reasons why:
1.**HTTP Responses**:

- **Error Code**: When there's an issue with authentication, the server should respond with an appropriate HTTP status code. For authentication failures, the standard code is 401 (Unauthorized). This informs the client (e.g., web browser) that authentication is required.
- **Reason Phrase**: Along with the status code, the server should include a brief reason phrase in the response header. For example, "Unauthorized" or "Authentication Required." This helps both users and developers quickly understand what went wrong.
- **Authorization Header**: If Basic Authentication is used, the server may prompt the client to provide credentials by including an "WWW-Authenticate" header in the response. This header informs the client that it needs to send credentials for authentication.
- **Example**:
     HTTP/1.1 401 Unauthorized
     WWW-Authenticate: Basic realm="Example"
     Content-Type: text/plain
     Content-Length: 46
Unauthorized: Authentication is required.

2.**HTML Pages**:

- **User-Friendly Message**:
In addition to the HTTP response, the HTML page presented to the user should include a clear and user-friendly error message. This message should inform the user about what went wrong and how to proceed.
- **Instructions**: If the error is due to incorrect credentials, provide instructions on what the user should do next, such as retrying with the correct username and password or resetting their password if necessary.
- **Avoid Specific Details**: While error messages should be informative, avoid revealing specific details that could aid attackers, such as whether the username or password was incorrect. Instead, use generic messages like "Incorrect username or password."
- **Example**:
     < html >

     < head >

< title > Unauthorized Access < /title >
     < /head >
     < body >

         < h1 >Unauthorized Access< /h1 >
         <p>Sorry, you are not authorized to access this resource.< /p >
         <p>Please check your credentials and try again.< /p >
     < /body >
     < /html >

**Why?**

- **Clarity**: Clear error messages help users understand what went wrong and how to resolve the issue, reducing frustration and confusion.
- **Security**: Providing generic error messages helps protect against information leakage, as detailed error messages could potentially reveal sensitive information to attackers.
- **User Guidance**: Including instructions on what to do next helps users take appropriate actions to resolve authentication issues, improving the overall user experience.
Bookmark this link also and consider OWASP fundamentals any time you interact with authentication. Applications developed with security in mind from inception have fewer vulnerabilities throughout their lifecycle.
Absolutely, keeping security at the forefront of development is crucial for creating robust and trustworthy applications. Bookmarking the OWASP (Open Web Application Security Project) website is a fantastic idea. OWASP provides a wealth of resources, including guidelines, best practices, and tools to help developers enhance the security of their applications.
By adhering to OWASP fundamentals during authentication and throughout the development lifecycle, developers can mitigate common security risks and vulnerabilities, such as injection attacks, broken authentication, sensitive data exposure, and more.
Here's the link to the OWASP website for your bookmark:
[OWASP Website](https://owasp.org/)
Remembering to consult OWASP resources regularly can help ensure that security remains a top priority in every stage of application development, leading to safer and more resilient software for users.
Bookmark and Review
bcrypt docs
Additional Questions
Looking ahead at this module’s course schedule, What do you look forward to learning?
I am looking forward more about AWS. Someone once told me to learn it when I was driving around as an Uber driver and we were talking about Software Development over in Silicon Valley. He stated that not a lot of developers have experience in it or proficient in AWS.  I am also looking forward to graphing and getting right back into REACT.
What are your learning goals after reading and reviewing the class README?
As I navigate my learning journey, I've set my sights on mastering Sequelize and delving into the intricacies of instance methods. While the road ahead may seem daunting, I'm fully committed to overcoming any challenges that come my way.
Breaking down the complexities of Sequelize into manageable chunks is my first step. I'll start with the basics, gradually building my understanding, and ensuring each concept is solid before moving forward.
Practice will be my cornerstone. Through hands-on projects and exercises, I'll immerse myself in Sequelize, experimenting with models, querying data, and refining my skills with instance methods.
Guidance from the Sequelize documentation and online tutorials will serve as my compass, providing detailed insights and practical examples to navigate through the intricacies of Sequelize effectively.
In times of uncertainty, I'll lean on the support of online communities, forums, and mentors. Their guidance and encouragement will bolster my confidence and propel me forward.
Embracing the inevitable challenges as opportunities for growth, I'll persist with determination and resilience. Each hurdle overcome will be a testament to my progress and a stepping stone towards mastery.
Regular reflection on my journey will ensure I stay on course, celebrating my successes and acknowledging areas for improvement. With each stride forward, I'll inch closer to my goal of mastering Sequelize and expanding my repertoire of skills.
In this pursuit of knowledge, I am both the student and the architect of my destiny, fueled by a relentless passion for learning and an unwavering commitment to excellence.

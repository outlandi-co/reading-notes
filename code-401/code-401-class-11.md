# Readings: Event Driven Applications

Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.
Review the Submission Instructions for guidance on completing and submitting this assignment.
Reading
Event Driven Programming
What native Node.js module allows us to get started with Event Driven Programming?
The native Node.js module that allows us to get started with Event Driven Programming is `events`. This module provides a way to handle events in Node.js, enabling developers to create custom event emitters and listeners, facilitating the implementation of event-driven architecture in their applications.
What is the value of Object Oriented Programming used in tandem with Event Driven Programming?
Object-Oriented Programming (OOP) and Event-Driven Programming (EDP) complement each other well and are often used together to create robust and modular software solutions.
Here's how OOP adds value when used alongside EDP:

1.**Encapsulation**: OOP promotes encapsulation, where data and behavior are bundled together within objects. This helps in managing the complexity of event-driven systems by encapsulating related data and functionality into cohesive units. For example, in a GUI application, you can encapsulate the state and behavior of UI elements (such as buttons, text fields) into objects, making it easier to handle their events.
2.**Abstraction**: OOP allows you to abstract away implementation details and focus on interfaces. This is useful in event-driven systems where you often need to define clear interfaces for event producers and consumers. By defining clear interfaces, you can decouple components, making your system more flexible and easier to maintain.
3.**Inheritance and Polymorphism**: Inheritance and polymorphism are powerful concepts in OOP that allow you to create hierarchies of related classes and substitute objects of one class with objects of another compatible class. This can be useful in event-driven systems for creating reusable components and handling events in a uniform way across different types of objects.
4.**Modularity and Reusability**: OOP promotes modularity and reusability through concepts like classes, objects, and modules. This is beneficial in event-driven systems where you can create reusable components that emit and respond to events. By encapsulating functionality into reusable objects, you can write cleaner and more maintainable code.
5.**Event Handling Patterns**: OOP provides patterns and techniques for managing event handling logic effectively. For example, you can use design patterns like Observer, Mediator, or Command to structure your event-driven codebase in a more organized and scalable manner.
Overall, combining OOP principles with event-driven programming techniques can lead to well-structured, maintainable, and scalable software systems.
Consider your knowledge of Event Driven Programming in the Web Browser, now explain to a non-technical friend how Event Driven Programming might be useful on the backend using Node.js.
Sure! Imagine you're planning a big party. Event-driven programming in the web browser is like planning activities for the guests at your party. For example, when someone clicks a button on a party website, like RSVPing to the event, the website reacts to that action by displaying a confirmation message or updating the guest list.
Now, let's talk about Node.js on the backend. Think of Node.js as the behind-the-scenes organizer of your party. It handles all the requests and responses, making sure everything runs smoothly. Event-driven programming in Node.js is like having a bunch of helpers who are always ready to jump into action whenever something happens.
For instance, let's say someone submits a form on your party website to request a song to be played. With event-driven programming in Node.js, you can set up a system where Node.js listens for this request. When the request comes in, Node.js triggers an event, like "playSong", and then takes the necessary actions, such as streaming the requested song to the party playlist.
This event-driven approach is really useful because it allows Node.js to handle multiple tasks simultaneously without getting bogged down. Just like at your party, where different activities can happen at the same time—some guests might be dancing, while others are chatting—Node.js can handle requests from multiple users at once, ensuring that everyone has a good time without any delays.
So, in summary, event-driven programming in Node.js helps make your backend code more responsive and efficient, just like having a team of helpful assistants at your party ensures everything runs smoothly for your guests!

Bookmark and Review
Node docs: events
Additional Questions
Looking ahead at this module’s course schedule, What do you look forward to learning?
I'm really looking forward to diving into the AWS portion of the course. Learning how to leverage cloud services like EC2, S3, and Lambda will not only enhance my understanding of backend infrastructure but also enable me to deploy and scale my applications more effectively.
Moreover, delving into React excites me because it's a powerful tool for building modern and responsive user interfaces. Mastering React will not only make me more proficient in frontend development but also allow me to create more engaging and intuitive experiences for users.
Exploring graph data structures is another aspect I'm eager to delve into. Graphs offer elegant solutions to complex problems, and understanding them will sharpen my problem-solving skills and broaden my understanding of data structures and algorithms.
Lastly, wireframing might seem like a small detail, but I believe it's crucial for setting the right foundation for any project. Proper planning and wireframing ensure that projects are well-structured from the start, leading to smoother development processes and more user-friendly applications.
Overall, I'm thrilled about the opportunities for growth and learning that lie ahead in this course, and I can't wait to dive in and make the most of them!

What are your learning goals after reading and reviewing the class README?
After reviewing the class README on Event Driven Applications, I'm genuinely enthusiastic about the learning journey ahead. Here are my personal learning goals:

1.I want to thoroughly understand the concept of Event Driven Programming and its relevance in both human interactions and software development. Recognizing how events drive actions in both worlds will deepen my understanding of this programming paradigm.
2.Mastering the Node event system and event-driven architecture is a priority for me. I aim to learn how events are raised, monitored, and responded to within JavaScript applications, enabling me to build more responsive and efficient systems.
3.Implementing the Observer pattern using Publish/Subscribe methodology intrigues me. Creating modular, event-based systems will not only enhance my coding skills but also empower me to design more scalable and maintainable applications.
4.I'm eager to gain hands-on experience in emitting events and handling them effectively within JavaScript applications. Utilizing tools like Express routes for HTTP requests will give me practical insights into event-driven programming.
5.Exploring real-world examples of event-driven programming, such as sending notifications or emails based on specific events, excites me. I'm eager to understand how these concepts translate into tangible solutions in software development.
6.Designing and implementing event-driven systems that are scalable and efficient is a key goal. I want to learn best practices for designing event-driven architectures that can handle complex interactions seamlessly.
7.Lastly, I'm eager to identify opportunities to leverage event-driven programming in various contexts, from UI interactions to server-side operations, and potentially explore its applications in future studies with frameworks like React.

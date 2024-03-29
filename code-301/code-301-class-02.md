reading-notes
Reading- Notes

React lifecycle

1.Based off the diagram, what happens first, the ‘render’ or the ‘componentDidMount’?
In React, during the lifecycle of a component, componentDidMount is invoked after the render method has been called and the component has been mounted onto the DOM (Document Object Model). Here’s the sequence of events:

Constructor: The component’s constructor is called.
Render: The render method is called, and it returns the JSX (or elements) to be rendered.
Component Mounts: The component is mounted onto the DOM.
ComponentDidMount: After the component has been mounted onto the DOM, componentDidMount lifecycle method is called. This is where you typically perform actions that need to happen after the component is rendered for the first time, such as fetching data from an API or setting up event listeners. So, componentDidMount happens after render. It’s a good place for operations that require access to the DOM or need to be executed after the initial render.
2. What is the very first thing to happen in the lifecycle of React?
In the lifecycle of a React component, the very first thing to happen is the initialization of the component. This involves the construction of the component instance. During this phase, the constructor of the component is called. The constructor is where you typically initialize state, bind event handlers, and perform other setup operations. It’s important to note that you should avoid side effects in the constructor, as it’s meant for initialization purposes. So, in summary, the initialization phase, including the invocation of the constructor, is the very first thing to happen in the lifecycle of a React component.

3. Put the following things in the order that they happen: componentDidMount, render, constructor, componentWillUnmount, React Updates
The correct order of the React lifecycle methods and events is as follows:

Constructor: This is the first method called when a component is initialized. It is used for initializing state and binding event handlers
Render: The render method is called after the constructor. It returns the JSX (or elements) to be rendered to the DOM.
React Updates: This happens after the initial render and includes updates to the component’s state or props, triggering a re-render of the component.
ComponentDidMount: This method is called after the component has been mounted onto the DOM. It’s invoked once after the initial render and is used for performing operations that require access to the DOM or for setting up subscriptions or timers.
ComponentWillUnmount: This method is called just before a component is unmounted and destroyed. It’s used for cleanup operations such as removing event listeners or cancelling timers to prevent memory leaks. So, the correct order is:
Constructor
Render
React Updates
ComponentDidMount
ComponentWillUnmount
4. What does componentDidMount do?
The componentDidMount lifecycle method is a method provided by React that is called after a component has been mounted onto the DOM (Document Object Model). It’s invoked once, immediately after the initial rendering of the component. Here’s what componentDidMount is typically used for:

DOM Manipulation: Since componentDidMount is called after the component is rendered and mounted onto the DOM, it’s a suitable place to perform any DOM manipulation tasks, such as interacting with the browser’s APIs, accessing DOM elements, or setting up third-party libraries that need access to the DOM.
Data Fetching: It’s common to fetch data from APIs or perform other asynchronous operations in componentDidMount. Since it’s called after the component is rendered, it’s safe to fetch data and update the component’s state based on that data.
Subscriptions and Event Listeners: componentDidMount is also a good place to set up subscriptions to external data sources, such as web sockets, or to add event listeners to the window or document. Overall, componentDidMount provides a convenient hook for performing actions that need to happen after the component is rendered for the first time and after it has been mounted onto the DOM.
Videos React State Vs Props

1. What types of things can you pass in the props?
In React, props (short for “properties”) are used to pass data from a parent component to a child component. Props can be of various types, including:

Primitive Data Types: You can pass primitive data types such as strings, numbers, booleans, and symbols as props. For example: <ChildComponent name=”John” age={25} isActive={true} />
Functions: You can pass functions as props. This is useful for allowing child components to communicate with their parent components by invoking functions passed down as props. For example: <ChildComponent onClick={handleClick} />
Objects: You can pass objects as props, allowing you to pass complex data structures from a parent component to a child component. For example: const person = { name: ‘John’, age: 25 }; <ChildComponent person={person} />
Arrays: You can pass arrays as props, enabling you to pass lists of items from a parent component to a child component. For example: const numbers = [1, 2, 3, 4, 5]; <ChildComponent numbers={numbers} />
React Elements: You can pass React elements (components) as props. This allows you to compose your UI by nesting components within each other. For example:
Callback Functions: You can pass callback functions as props, allowing child components to communicate with their parent components by invoking these functions. For example:
<ChildComponent onChange={handleChange} /> Overall, props in React provide a flexible mechanism for passing data and behavior between components in a React application.

2. What is the big difference between props and state?
The big difference between props and state in React lies in how they are used and where they are managed:

Props (Properties):
Props are used to pass data from a parent component to a child component.
They are immutable and read-only within the child component.
Props are passed down from the parent component and cannot be modified by the child component.
Changes to props must be initiated by the parent component.
Props are passed as attributes to components when they are declared in JSX.
Props are external inputs to the component.
State:
State is used to manage internal component data that may change over time.
State is mutable and can be modified using the setState method.
State is managed within the component itself and can be modified based on user actions, lifecycle events, or other factors.
Changes to state trigger re-rendering of the component.
State is initialized within the constructor or through class properties using the useState hook in functional components.
State is internal to the component and represents its own view of data. In summary, the key differences between props and state are that props are passed from parent to child components and are immutable within the child, while state is managed internally within a component and can be modified using setState. Understanding when to use props and when to use state is crucial for building React applications efficiently and effectively.
3. When do we re-render our application?
In React, the re-rendering of the application occurs under certain conditions, typically triggered by changes in component state or props. Here are the main scenarios when a re-render may occur:

State Changes: When the setState method is called within a component, React will re-render that component and its child components to reflect the updated state.
Props Changes: When a parent component passes new props to a child component, React will re-render the child component to reflect the changes in props.
Force Update: In some cases, you might explicitly call the forceUpdate method on a component, which will cause it to re-render, bypassing the usual checks for state and props changes.
Context Changes: If a component is consuming context using the useContext hook or the Context.Consumer component, and the context value changes, React will re-render the component and its children to reflect the new context value.
Lifecycle Methods: Certain lifecycle methods, such as componentDidUpdate and shouldComponentUpdate, can also trigger re-renders based on specific conditions defined within these methods.
Event Handlers: User interactions such as clicks, input changes, or other events may trigger state updates, which in turn can lead to re-renders of the relevant components.
Async Operations: Asynchronous operations like data fetching from APIs using fetch or axios, or timers set using setTimeout or setInterval, may lead to state updates and subsequent re-renders when the asynchronous operation completes. In summary, React re-renders components in response to changes in state, props, context, or other factors that affect the UI. Understanding when and why re-renders occur is important for optimizing performance and managing component updates effectively.
4. What are some examples of things that we could store in state?
In React, you can store various types of data in component state, depending on the requirements of your application. Here are some examples of things that you could store in state:

Form Input Values: You can store the values of form input fields in state, allowing you to capture user input and update it dynamically as the user types.

UI State: You can store UI-related state such as whether a modal is open or closed, the current active tab in a tabbed interface, or the visibility of a dropdown menu.

User Authentication State: You can store the authentication status of a user, such as whether they are logged in or logged out, and display different UI elements or routes based on their authentication status.

API Data: You can store data fetched from APIs in state, allowing you to display dynamic content based on the retrieved data. For example, you could store a list of posts fetched from a blog API.

Error Messages: You can store error messages in state, allowing you to display them to the user when something goes wrong, such as an invalid form submission or a failed API request.

Loading State: You can store loading indicators or flags in state to indicate when data is being fetched from an API or when a long-running operation is in progress.

Toggle State: You can store boolean values in state to represent toggles or switches, such as whether a checkbox is checked or a button is enabled/disabled.

Pagination State: You can store pagination-related state, such as the current page number and the number of items per page, allowing you to implement pagination in your application.

These are just a few examples of the types of data that you can store in component state. In general, state is used to represent any data that may change over time and affect the rendering of the component.

reading-notes
1. What is a “component”?
A “component” in software engineering refers to a modular, reusable, and self-contained unit of software that encapsulates a specific functionality or behavior within a larger system. Components are typically designed to interact with other components through well-defined interfaces, allowing for easy integration and composition to build complex systems.

2. What are the characteristics of a component?
The characteristics of a component include:

Modularity: Components are self-contained and can be easily assembled and disassembled within a system without affecting other components.

Reusability: Components are designed to be reused in different contexts or applications, reducing development time and effort.

Encapsulation: Components encapsulate their implementation details, hiding the internal workings and exposing only well-defined interfaces to interact with other components.

Interoperability: Components are designed to work together seamlessly, typically through standardized interfaces or protocols, regardless of the underlying technologies or languages used to implement them.

Composability: Components can be combined or composed together to create larger systems or applications, facilitating scalability and flexibility in software design.

Independence: Components should ideally be independent of each other, allowing for easier maintenance, testing, and upgrades without affecting other parts of the system.

3. What are the advantages of using component-based architecture?
The advantages of using a component-based architecture include:

Reusability: Components can be reused across different projects or applications, saving time and effort in development.

Modularity: Components promote a modular design approach, making it easier to manage and maintain complex systems by breaking them down into smaller, more manageable parts.

Scalability: Component-based architectures are inherently scalable, as new components can be added or existing ones modified without impacting the entire system.

Ease of Development: Developers can focus on designing and implementing individual components independently, which can lead to faster development cycles and easier debugging.

Flexibility: Components can be easily replaced or upgraded without affecting other parts of the system, providing flexibility in adapting to changing requirements or technologies.

Improved Collaboration: Since components are self-contained and have well-defined interfaces, multiple development teams can work on different components simultaneously without interfering with each other’s work.

Maintenance: Maintenance becomes easier as components are independent entities, allowing for targeted updates or fixes without affecting the entire system.

Overall, component-based architectures promote better code organization, reuse, and maintainability, leading to more efficient and robust software systems.

1. What is “props” short for?
In React, “props” is short for “properties”. Props are a mechanism for passing data from a parent component to a child component. They are immutable and are used to customize or configure a component’s behavior and appearance.

2. How are props used in React?
Props are passed to components as attributes in JSX and are accessed within the component using the props object. Here’s how props are typically used in React:

Passing Props: When rendering a component, you can pass props to it by specifying attributes in JSX. For example:
<MyComponent name="John" age={30} />
Accessing Props: Inside the component, props are accessed through the props object. For example:
function MyComponent(props) {
  return <div>Hello, {props.name}. You are {props.age} years old.</div>;
}
Using Props: Once props are passed to a component, they can be used to dynamically render content or configure the behavior of the component. For example, you can use props to customize the appearance of a component or conditionally render certain elements based on the props passed to it.
3. What is the flow of props?
In React, props flow in a unidirectional manner, from parent components to child components. This means that props are passed down from parent components to their child components, but not in the reverse direction. The flow of props ensures that child components remain isolated and can be easily reused or composed within different parent components.

Here’s the typical flow of props in React:

Parent Component: Props are defined and passed from a parent component when rendering its child components.
Child Component: Props are received and accessed by the child component, allowing it to use the data passed from the parent component.
Child-to-Child Communication: If necessary, props can also be passed from a parent component to its nested child components, creating a hierarchical flow of data.
This unidirectional flow of props helps maintain the separation of concerns and makes it easier to reason about the state and behavior of individual components within a React application.
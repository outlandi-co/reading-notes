
# Reading Assignment 04
Reading
Learn HTML
Creating Hyperlinks
## To create a basic link, we wrap text or other content inside what element?
* To create a basic link in HTML, you wrap the text or other content inside an <a> (anchor) element. 
* <a> is the anchor element.
* href is the attribute specifying the destination URL that the link points to.
* "https://example.com" is the value of the href attribute, representing *the destination URL.
*Link Text is the content that will be displayed as the clickable link.

## The href attribute contains what information?
The href attribute in HTML contains the URL (Uniform Resource Locator) or the web address to which the hyperlink points. It specifies the target of the link. When a user clicks on the link, the browser navigates to the URL specified in the href attribute.
the href attribute contains the URL "https://www.example.com", so when the link is clicked, the browser will navigate to the website at that URL.

## What are some ways we can ensure links on our pages are accessible to all readers?
* Ensuring that links on web pages are accessible to all readers is crucial for providing an inclusive browsing experience. Here are some ways to achieve this:
* Use Descriptive Text: Write descriptive link text that clearly indicates the destination or purpose of the link. Avoid using generic terms like "click here" or "read more." Instead, use meaningful phrases that convey the context of the link.
* Use Title Attribute: Include a title attribute with additional information about the link. Screen readers can read out the title attribute, providing more context for users who rely on auditory cues.
* Ensure Link Visibility: Ensure that links are visually distinguishable from surrounding text. Use styling such as underlining, color changes, or icons to make links stand out.
* Keyboard Accessibility: Ensure links can be easily navigated using the keyboard alone. Users should be able to tab through links in a logical order and activate them using the Enter key.
* Skip Links: Include "skip links" at the beginning of your page to allow keyboard users to skip repetitive navigation and jump directly to the main content.
* Provide Focus Styles: Ensure links have visible focus styles so that keyboard users can easily identify which link is currently focused. This helps users navigate through links without relying solely on visual cues.
* Semantic HTML: Use semantic HTML elements like <a> for links, <button> for buttons, and <input type="button"> for interactive elements. This ensures assistive technologies can interpret the purpose of the element correctly.
* Test with Accessibility Tools: Use accessibility testing tools and screen readers to evaluate the accessibility of your links and overall page structure. Identify and address any accessibility issues that are discovered.
* By implementing these practices, you can make sure that links on your web pages are accessible to all users, including those with disabilities or using assistive technologies
CSS Layout
* CSS Layout: Normal Flow CSS Layout: Positioning
## What is meant by “normal flow”?
In web design and layout, "normal flow" refers to the default behavior of HTML elements as they are rendered on a web page without any additional styling or positioning applied. In the normal flow, elements are displayed one after another in the order they appear in the HTML document, typically from top to bottom and left to right (for languages that read left-to-right).
The key characteristics of elements in the normal flow include:
Block-level and Inline Elements: Elements are displayed either as block-level or inline elements based on their default display property. Block-level elements typically start on a new line and take up the full width available, while inline elements flow within the text and only take up as much width as necessary.
Vertical Stacking: Block-level elements are stacked vertically on top of each other, with each element taking up its own vertical space.
Document Order: Elements are displayed in the order they appear in the HTML document, unless modified by CSS positioning properties.
Flow Direction: Elements are laid out based on the writing mode of the language, flowing from top to bottom and left to right in languages like English.
When additional CSS properties such as positioning, floating, or flexbox/grid layouts are applied to elements, they can be taken out of the normal flow, allowing for more complex layouts and designs. However, understanding and leveraging the normal flow is fundamental to creating well-structured and accessible web layouts.

## What are a few differences between block-level and inline elements?
Block-level and inline elements in HTML have several differences in terms of their default behavior, layout, and how they interact with other elements on a webpage. Here are a few key differences:
Display Behavior:
Block-level elements:
Start on a new line.
Occupy the full width available.
Allow setting the width, height, margin, and padding.
Inline elements:
Do not start on a new line.
Occupy only as much width as necessary.
Do not allow setting the width, height, margin, and padding (except for left and right margins/paddings).
Content Model:
Block-level elements typically contain other block-level and inline elements, as well as text and other content.
Inline elements are typically contained within block-level elements and can only contain other inline elements or text.
Default Elements:
Common block-level elements include <div>, <p>, <h1> to <h6>, <ul>, <ol>, and <li>.
Common inline elements include <span>, <a>, <strong>, <em>, <img>, <br>, and <input> (in some cases).
Line Breaks:
Block-level elements cause a line break before and after themselves.
Inline elements do not cause line breaks and flow within the text of a line.
Nested Elements:
Block-level elements can contain other block-level and inline elements, as well as text.
Inline elements cannot contain block-level elements.
Default CSS Display Property:
The default display property value for block-level elements is block.
The default display property value for inline elements is inline.
Understanding these differences is essential for effectively structuring and styling web content, as well as creating layouts that meet design requirements.

## ___ positioning is the default for every html element.
Static" positioning.
Static positioning is the default positioning scheme for every HTML element. When an element is statically positioned, it follows the normal flow of the document. It is positioned according to its place in the document layout, without any adjustments made by positioning properties such as top, right, bottom, or left. Additionally, static positioned elements are not affected by the z-index property.
In CSS, if no positioning scheme is specified for an element, it is considered to be statically positioned. This is in contrast to other positioning schemes such as relative, absolute, fixed, or sticky positioning, which modify the position of the element relative to its normal position in the document flow.

## Name a few advantages to using absolute positioning on an element.
Using absolute positioning for an element in CSS can offer several advantages in certain scenarios. Here are a few:
Precise Placement: Absolute positioning allows you to precisely place an element relative to its containing block or nearest positioned ancestor. This can be useful for creating custom layouts or positioning elements with pixel-perfect accuracy.
Layering and Z-index: Absolute positioning allows you to control the stacking order of elements using the z-index property. This can be beneficial for layering elements on top of each other, such as creating overlays, tooltips, or dropdown menus.
Breaking the Document Flow: Absolute positioning removes the element from the normal document flow, allowing other elements to flow around it. This can be advantageous when you want to position an element without affecting the layout of surrounding content.
Creating Overlays and Modals: Absolute positioning is commonly used to create overlays, modals, or pop-up dialogs that appear above other content on the page. By positioning these elements absolutely, you can ensure they appear in the desired location regardless of the position of other elements.
Responsive Design: While absolute positioning is often associated with fixed positioning, it can also be used responsively. By using relative units (such as percentages) or media queries, you can make absolutely positioned elements adapt to different screen sizes or device orientations.
Animating Position: When combined with CSS animations or transitions, absolute positioning can be used to create dynamic effects by animating an element's position or size. This can add visual interest and interactivity to your web pages.
While absolute positioning offers these advantages, it's essential to use it judiciously and consider its impact on accessibility, responsiveness, and maintainability. Overuse of absolute positioning can lead to layout issues, especially on different screen sizes or when content changes dynamically.

## What is a key difference between fixed positioning and absolute positioning?
A key difference between fixed positioning and absolute positioning lies in how they are anchored within the document layout:
Fixed Positioning:
An element with fixed positioning is positioned relative to the viewport, meaning it remains in a fixed position on the screen even as the user scrolls the page.
The element is removed from the normal document flow, and its position is determined by its top, right, bottom, and left properties relative to the viewport.
Fixed positioning is commonly used for elements like navigation bars, headers, or footers that should remain visible regardless of the user's scroll position.
Absolute Positioning:
An element with absolute positioning is positioned relative to its nearest positioned ancestor or the initial containing block if no ancestor is positioned.
The element is removed from the normal document flow, but its position is determined by its top, right, bottom, and left properties relative to its containing block.
Absolute positioning is commonly used for elements like tooltips, pop-up menus, or modal dialogs that need to be positioned relative to a specific parent element or container.
In summary, the key difference is that fixed positioning is relative to the viewport, while absolute positioning is relative to a positioned ancestor. Fixed elements stay in the same position even when the page is scrolled, whereas absolute elements move with their nearest positioned ancestor.

Learn JS
Functions – Reusable Blocks of Code
## Describe the difference between a function declaration and a function invocation.
the differences between a function declaration and a function invocation:
Function Declaration:
A function declaration is a way of defining a function in JavaScript.
It involves declaring the function using the function keyword followed by the function name and a set of parentheses for parameters, if any, and then a code block enclosed in curly braces {} containing the function's implementation.
Function declarations are hoisted in JavaScript, meaning they are moved to the top of their scope during the compilation phase, so they can be called before they are defined in the code.
Function Invocation (Function Call):
Function invocation, also known as a function call, is the process of executing a function.
It involves using the function name followed by parentheses () containing any arguments that need to be passed to the function.
Function invocation causes the function's code block to be executed, with any provided arguments being passed to the function parameters.
In summary, a function declaration is the act of defining a function, specifying its name and implementation, while a function invocation is the act of calling or executing the function, triggering the execution of its code block with any provided arguments.

## What is the difference between a parameter and an argument?
In programming, particularly in the context of functions, the terms "parameter" and "argument" refer to different concepts:
Parameter:
A parameter is a variable listed in the function declaration or definition.
It acts as a placeholder for the value that will be provided when the function is called.
Parameters are essentially the input variables that a function expects to receive in order to perform its task.
Parameters are defined in the function declaration and represent the data that the function will work with.
Parameters are local variables within the scope of the function.
Argument:
An argument is the actual value that is passed to the function when it is called.
It is the data that is supplied to the function for it to process.
Arguments are provided when the function is invoked, and they correspond to the parameters defined in the function declaration.
Arguments can be variables, literals, or expressions.
In summary, a parameter is a variable in a function declaration that represents an input value, while an argument is the actual value passed to the function when it is called, corresponding to the parameters defined in the function declaration.
Miscellaneous
6 Reasons for Pair Programming
##Pick 2 benefits to pair programming and reflect on how these benefits could help you on 
your coding journey.
Two benefits of pair programming are improved code quality and increased learning opportunities.
Improved Code Quality:
Pair programming involves two developers working together on the same codebase, which often leads to better code quality. By having two sets of eyes on the code, potential bugs, logic errors, and code inefficiencies can be caught and addressed more effectively.
Through collaboration and discussion, pair programming encourages best practices, code reviews, and refactoring, resulting in cleaner, more maintainable code.
Reflection: As an individual coder, I may sometimes overlook certain aspects of my code or make mistakes that go unnoticed. Pair programming would allow me to collaborate with another developer, providing an opportunity to catch errors early, discuss different approaches, and ultimately produce higher-quality code. This collaborative approach can lead to better solutions and reduce the likelihood of introducing bugs or technical debt into the codebase.
Increased Learning Opportunities:
Pair programming promotes knowledge sharing and continuous learning. Developers can learn from each other's experiences, skills, and perspectives, leading to professional growth and development.
Working with someone else exposes you to different coding styles, problem-solving techniques, and software development practices. This exposure broadens your understanding of programming concepts and tools.
Reflection: Throughout my coding journey, I recognize the importance of continuous learning and expanding my skill set. Pair programming presents an excellent opportunity to learn from others and gain insights into alternative approaches or techniques that I may not have considered on my own. By collaborating with someone with different experiences and expertise, I can enhance my problem-solving abilities, learn new programming concepts, and improve my overall proficiency as a developer.

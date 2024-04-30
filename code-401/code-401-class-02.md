# Readings: Express, NPM, TDD, CI/CD

Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.
Review the Submission Instructions for guidance on completing and submitting this assignment.
Reading

An introduction to NodeJS and Express

Explain middleware, answer as though I were a non-technical recruiter.
Middleware is like a helpful assistant that manages communication between different parts of a website or web app. It ensures things run smoothly by handling tasks like checking requests, managing data, or dealing with errors before passing them along. It's like having someone to make sure everything's in order behind the scenes.

## Express the most popular __ ______

Express is the most popular web application framework for Node.js.

## Express is “unopinionated.” What does that mean?

When we say Express is "unopinionated," it means that Express doesn't enforce strict rules or tell you how you should build your web application. Instead, it gives you the freedom to choose your own tools, patterns, and structure for developing your application. It's like a blank canvas where you can paint your own picture, rather than being guided by predefined rules or opinions.

## What is a module and why is modularity useful to us as developers?

A module is like a small, self-contained unit of code that performs a specific task or provides a set of related functions. It's kind of like a building block that developers can use to build larger and more complex applications.

Modularity, or breaking down code into these smaller modules, is useful to developers for a few reasons:

1. **Organization:** Breaking code into modules helps keep things organized and manageable. Instead of having one giant file with all the code in it, developers can split it into smaller, more focused modules that are easier to understand and maintain.

2. **Reuse:** Modules can be reused across different parts of an application or even across different projects. This saves time and effort, as developers don't have to reinvent the wheel every time they need to perform a common task or implement a specific feature.

3. **Collaboration:** Modularity makes it easier for developers to collaborate on projects. Since modules are self-contained and focused on specific tasks, different team members can work on different modules independently without stepping on each other's toes.

Overall, modularity helps make code more organized, reusable, and collaborative, which ultimately leads to more efficient and maintainable software development.

## What is NPM?

### What version of npm are you running on your machine?

npm@10.5.1 /opt/homebrew/lib/node_modules/npm

### What command would you type to install a library/package called ‘jshint’ into your node project?

npm install jshint

## What is TDD?

### Explain why tests are important. Please explain as though I were your non technical elder

Tests are like safety checks for our software, dear elder. Just as we check the locks on our doors before leaving the house, tests ensure that our software works as expected and doesn't have any hidden issues. Think of tests as our way of making sure that everything in our software is in good order before it's used by others.
You see, without tests, it's like driving a car without brakes. We might not notice any problems at first, but eventually, something unexpected could happen and cause a big problem. Tests help us catch those unexpected issues early on, before they have a chance to cause trouble.
And just like how we feel more confident knowing that our house is secure, tests give us peace of mind knowing that our software is reliable and won't let us down when we need it most. So, in simple terms, tests are important because they help us build software that we can trust and rely on, just like we trust the locks on our doors to keep us safe.

### What are three expected benefits of testing

1. **Reliability:** Testing helps ensure that our software behaves predictably and consistently. Just like how we check the brakes on a car to ensure it stops when we need it to, testing helps us catch any bugs or errors in our software before they cause problems for users. This reliability builds trust and confidence in our software.
2. **Maintenance:** Testing makes it easier for us to make changes to our code without accidentally breaking existing functionality. Just like how we regularly maintain our home appliances to keep them working smoothly, testing allows us to refactor or add new features to our software with confidence that we're not introducing any unintended side effects.
3. **Documentation:** Tests serve as documentation of how our code should behave. Just like how we refer to a recipe to cook a favorite dish, tests provide a clear and concise description of the expected behavior of our software. This makes it easier for developers to understand and work with the code, even if they didn't originally write it.

### Name at lest 2 individual pitfalls and at least 2 team pitfalls commonly encountered while writing tests

**Individual pitfalls:**

1. **Overcomplicating tests:** Sometimes, developers can fall into the trap of writing tests that are overly complex or test too many things at once. Just like how a recipe with too many ingredients can be overwhelming, tests that are too complicated can be difficult to understand and maintain. It's important to keep tests simple and focused on testing one specific aspect of the code at a time.
2. **Neglecting edge cases:** Another common pitfall is neglecting to test edge cases or unusual scenarios. Just like how we sometimes forget to account for special dietary restrictions when cooking for guests, developers may forget to test for rare but important scenarios in their code. Neglecting edge cases can lead to bugs slipping through unnoticed and causing problems for users.
**Team pitfalls:**
1.**Lack of communication:** One common team pitfall is a lack of communication about testing strategies and expectations. Just like how a recipe can turn out differently if everyone in the kitchen isn't on the same page, inconsistent testing practices within a team can lead to confusion and inefficiency. It's important for team members to communicate openly about their testing approach and ensure everyone is following the same standards.
2.**Testing bottlenecks:** Another challenge teams may encounter is depending too heavily on a single team member to write all the tests. Just like how a kitchen can become backed up if only one person is doing all the cooking, relying on one person to write all the tests can slow down development and create dependencies. It's important for teams to distribute testing responsibilities evenly and encourage collaboration to ensure testing efforts are efficient and effective.

CI/CD

### What are three benefits of Continuous Integration?

1.**Early Bug Detection:** Continuous Integration allows developers to integrate their code changes frequently, often several times a day. With each integration, automated tests are run to detect any bugs or errors introduced by the new code. By catching issues early in the development process, teams can address them swiftly, preventing them from escalating into larger problems later on.
2.**Improved Code Quality:** Continuous Integration encourages developers to write cleaner, more modular code. By integrating changes frequently and running automated tests, CI systems ensure that code adheres to coding standards and best practices. This leads to higher code quality and reduces the likelihood of bugs or issues in the final product.
3.**Faster Feedback Loop:** Continuous Integration provides rapid feedback to developers about the quality of their code changes. When a developer submits a new change, they receive immediate feedback from the CI system on whether their code passes the automated tests. This quick feedback loop enables developers to identify and address issues promptly, leading to faster iteration and delivery of features.

### What is the difference between Continuos Delivery and Continuous Deployment?

Continuous Delivery and Continuous Deployment are both practices used in the software development lifecycle, but they differ in their approach to releasing changes to production.
**Continuous Delivery:**
Continuous Delivery (CD) is a practice where software is built, tested, and prepared for release automatically and frequently. In Continuous Delivery, every code change that passes the automated tests is potentially releasable to production. However, the actual deployment to production is still a manual process. In other words, the software is always in a deployable state, but the decision to release it to production is made manually by the development team.
**Continuous Deployment:**
Continuous Deployment (CD) takes Continuous Delivery a step further. In Continuous Deployment, every code change that passes the automated tests is automatically deployed to production without any human intervention. This means that as soon as a change is merged into the main branch and passes all tests, it is automatically released to production and made available to users. Continuous Deployment streamlines the release process and allows for faster delivery of features and fixes to end-users.
In summary, the main difference between Continuous Delivery and Continuous Deployment lies in the final step of the deployment process. While Continuous Delivery requires manual intervention to release changes to production, Continuous Deployment automates this step, allowing changes to be deployed automatically as soon as they pass all tests.

### Explain how GitHub fits into this process assuming the listener comes from a non-technical background

Imagine GitHub as a big shared folder where everyone in a team keeps their work for a project. In our case, this "work" is the code for a software application.

1.**Storing Code:** Developers use GitHub to store their code. It's like having a safe place where everyone can keep their parts of the project organized. Each developer can contribute their code to the project by adding it to GitHub.
2.**Collaboration:** Just like how everyone in a family can share photos in a shared photo album, developers can share their code with each other on GitHub. They can see what changes others are making, discuss them, and work together to improve the code.
3.**Version Control:** GitHub keeps track of all the changes made to the code over time. It's like having a time machine that allows us to go back and see what the code looked like at different points in time. This is helpful if we need to fix a bug or undo a change that didn't work out.
4.**Integration with CI/CD:** GitHub can also work together with tools for Continuous Integration and Continuous Deployment (CI/CD). These tools help automate the process of testing and releasing the code. So, when developers make changes to the code and push them to GitHub, the CI/CD tools can automatically run tests to make sure everything still works as expected and deploy the changes to the live application if they pass.
In simple terms, GitHub is like a big, organized filing cabinet for storing and sharing code, and it plays a crucial role in enabling collaboration, version control, and automation in software development projects.

### What are your learning goals after reading and reviewing the class README?

"I find routes, middleware, and testing to be quite intimidating. While I'm excited to gain more exposure to them, I feel the need to focus more on understanding these concepts. Testing, especially when it comes to code challenges, still feels unclear to me. However, I'm hopeful that with more practice, I'll be able to grasp these concepts better."

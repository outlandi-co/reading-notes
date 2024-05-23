# Readings: AWS: Events

Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.
Review the Submission Instructions for guidance on completing and submitting this assignment.
Reading
AWS SQS vs SNS
What is the difference betweeen SQS and SNS?
Amazon Simple Queue Service (SQS) and Amazon Simple Notification Service (SNS) are both messaging services offered by AWS, but they serve different purposes and have different use cases. Here are the key differences between SQS and SNS:

## Amazon Simple Queue Service (SQS)

1.**Type**: SQS is a message queue service.
2.**Use Case**: It's used for decoupling the components of a distributed system. Producers send messages to a queue, and consumers pull and process these messages at their own pace.
3.**Message Delivery**: Messages are delivered once and are guaranteed to be processed at least once. However, SQS does not guarantee the order of message processing (except with FIFO queues).
4.**Processing**: Messages are processed asynchronously by one or more consumers.
5.**Features**:

- **Standard Queue**: Offers high throughput, at-least-once delivery, and best-effort ordering.
- **FIFO Queue**: Guarantees exactly-once processing and maintains the order in which messages are sent and received.

6.**Visibility Timeout**: When a message is received by a consumer, it becomes invisible to other consumers for a specified period (visibility timeout) to allow the first consumer to process and delete it.
7.**Use Cases**: Task queues, background job processing, order processing systems.

### Amazon Simple Notification Service (SNS)

1.**Type**: SNS is a pub/sub (publish/subscribe) messaging service.
2.**Use Case**: It's used for sending notifications or messages to a large number of subscribers. It allows publishers to send messages to multiple subscribers simultaneously.
3.**Message Delivery**: Messages are pushed to multiple subscribers (e.g., SQS queues, Lambda functions, HTTP endpoints, email, SMS).
4.**Processing**: Messages are delivered immediately to all subscribers. Each subscriber processes the message independently.
5.**Features**:

- **Fan-out Pattern**: Messages can be sent to multiple endpoints, allowing for high scalability and parallel processing.
- **Multiple Protocols**: Supports various protocols including HTTP/HTTPS, SQS, Lambda, email, and SMS.

6.**Subscription**: Subscribers need to subscribe to topics to receive messages. Publishers send messages to topics, and SNS handles the distribution.
7.**Use Cases**: Sending notifications to distributed systems, mobile push notifications, alerting and monitoring systems, real-time updates.

### Summary

- **SQS** is ideal for decoupling and buffering the communication between different components or microservices within a distributed system. It is best for asynchronous task processing where the order of message processing may or may not be important.
- **SNS** is suitable for broadcasting messages to multiple endpoints (subscribers) in real-time. It is best for sending notifications and alerts where the same message needs to be delivered to multiple services or users.
By leveraging both SQS and SNS together, you can create highly scalable, decoupled systems where SNS topics broadcast messages to multiple SQS queues or other endpoints for further processing.
What are some use cases for both SNS and SQS?
Both Amazon Simple Queue Service (SQS) and Amazon Simple Notification Service (SNS) are versatile services with a variety of use cases. Below are some common scenarios where each service, as well as both in combination, can be effectively utilized:

### Use Cases for Amazon SQS

1. **Task Queues**:
   - **Background Job Processing**: SQS can be used to manage background jobs such as image processing, data transformation, or video encoding. Jobs are placed in the queue and workers process them asynchronously.
   - **Order Processing**: In e-commerce platforms, order details can be queued for processing. This ensures that each order is handled in turn and can be retried in case of failure.
2. **Decoupling Microservices**:
   - **Service Decoupling**: SQS allows different parts of an application to communicate without being directly connected. For instance, a web server can place user requests into a queue, which are then processed by a backend service.
   - **Load Leveling**: If the rate at which requests arrive varies greatly, SQS can help smooth out these bursts, ensuring that backend services are not overwhelmed.
3. **Message Buffering**:
   - **Rate Limiting**: In cases where the producer of messages operates at a different speed than the consumer, SQS can buffer the messages, ensuring a steady flow.
4. **Retry Logic**:
   - **Reliable Processing**: SQS can be used to ensure messages are not lost and are retried if processing fails. This is crucial in scenarios where message delivery reliability is important.

### Use Cases for Amazon SNS

1. **Broadcasting Messages**:
   - **Real-Time Notifications**: SNS is ideal for sending notifications to users in real-time, such as alerting users about system outages, status updates, or new content availability.
   - **Fan-Out Messaging**: A single message can be broadcasted to multiple subscribers. This is useful for sending updates to multiple systems or services simultaneously.
2. **Mobile Push Notifications**:
   - **Mobile Apps**: SNS can be used to send push notifications to mobile devices across various platforms (iOS, Android, etc.), informing users about important updates or events.
3. **Email and SMS Notifications**:
   - **User Alerts**: SNS can send notifications via email or SMS to users, which is useful for alert systems, marketing campaigns, and user engagement.
4. **Event-Driven Systems**:
   - **Triggering AWS Lambda Functions**: SNS can trigger AWS Lambda functions to handle events, enabling event-driven computing and serverless architectures.

### Combined Use Cases for SNS and SQS

1. **Message Fan-Out with Queue Processing**:
   - **Complex Workflows**: An SNS topic can send messages to multiple SQS queues. Each queue can then be processed by different microservices. For example, a new user registration event can notify billing, marketing, and user profile services via separate queues.
   - **Parallel Processing**: SNS can fan out messages to multiple queues, allowing parallel processing of tasks. This improves system scalability and fault tolerance.
2. **Handling Multiple Subscribers**:
   - **Diverse Endpoints**: A single SNS message can be delivered to multiple endpoints such as HTTP/S endpoints, email, SMS, and multiple SQS queues. This allows different systems to react to the same event in various ways.
3. **Event Notification System**:
   - **Multi-Channel Alerts**: In monitoring and alerting systems, an event can trigger notifications to administrators via email (SNS), log it to a queue for later processing (SQS), and invoke a Lambda function for immediate remedial action.
By leveraging both SQS and SNS, you can build robust, scalable, and decoupled systems that handle diverse workloads and notification needs efficiently.
AWS SNS and SQS
Describe how to use SQS and SNS in a “fanout” pattern.
Using Amazon Simple Notification Service (SNS) and Amazon Simple Queue Service (SQS) in a "fanout" pattern involves SNS distributing messages to multiple SQS queues, enabling different services to process the messages concurrently. This pattern is highly effective for decoupling systems and scaling applications. Here's a detailed guide on how to implement the fanout pattern with SNS and SQS:

### Steps to Implement the Fanout Pattern

1. **Create an SNS Topic**
   - **Navigate to the SNS console**: Open the Amazon SNS console.
   - **Create a topic**: Click on "Create topic" and choose a name and type (standard or FIFO). Standard topics are typically used for fanout patterns due to their high throughput and at-least-once delivery guarantee.
2. **Create SQS Queues**
   - **Navigate to the SQS console**: Open the Amazon SQS console.
   - **Create queues**: Create one or more SQS queues that will subscribe to the SNS topic. For each queue, configure attributes as needed (e.g., default visibility timeout, message retention period).
3. **Subscribe SQS Queues to the SNS Topic**
   - **Subscribe queues**: In the SNS console, go to the topic you created and select "Create subscription".
   - **Select protocol and endpoint**: Choose "SQS" as the protocol and enter the ARN of the SQS queue as the endpoint. Repeat this step for each SQS queue you want to subscribe.
   - **Confirm subscriptions**: Ensure each SQS queue has successfully subscribed to the SNS topic. You may need to confirm the subscription depending on the queue policies.

4. **Configure IAM Permissions**
   - **Allow SNS to send messages to SQS**: Ensure that SNS has the necessary permissions to send messages to the SQS queues. This typically involves setting up an appropriate policy for each SQS queue.
   - **Example SQS Queue Policy**:

     ```json
     {
       "Version": "2012-10-17",
       "Id": "SQSPolicy",
       "Statement": [
         {
           "Effect": "Allow",
           "Principal": {
             "Service": "sns.amazonaws.com"
           },
           "Action": "sqs:SendMessage",
           "Resource": "arn:aws:sqs:REGION:ACCOUNT_ID:QUEUE_NAME",
           "Condition": {
             "ArnEquals": {
               "aws:SourceArn": "arn:aws:sns:REGION:ACCOUNT_ID:TOPIC_NAME"
             }
           }
         }
       ]
     }
     ```

   - Attach this policy to each SQS queue to ensure SNS can deliver messages.
5. **Publish Messages to SNS Topic**
   - **Publish messages**: When you have an event or message to distribute, publish it to the SNS topic. This can be done via the AWS Management Console, AWS CLI, or programmatically using the AWS SDKs.
   - **Example using AWS CLI**:

     ```sh
     aws sns publish --topic-arn arn:aws:sns:REGION:ACCOUNT_ID:TOPIC_NAME --message "Your message"

6.**Consume Messages from SQS Queues**

- **Retrieve messages**: Each subscribed service or application can then retrieve messages from its respective SQS queue at its own pace.
- **Process messages**: Consumers process the messages, performing the tasks relevant to their specific function.

### Example Use Case: Order Processing System

**Scenario**: An e-commerce platform processes new orders, updates inventory, and sends notifications when an order is placed.

1.**Create SNS Topic**:

- Topic Name: `OrderEventsTopic`

2.**Create SQS Queues**:

- Queues: `OrderProcessingQueue`, `InventoryUpdateQueue`, `NotificationQueue`
3.**Subscribe Queues to SNS Topic**:
- Subscribe `OrderProcessingQueue` to `OrderEventsTopic`
- Subscribe `InventoryUpdateQueue` to `OrderEventsTopic`
- Subscribe `NotificationQueue` to `OrderEventsTopic`
4.**Configure IAM Permissions**:
- Ensure each SQS queue allows messages from `OrderEventsTopic`.
5.**Publish Order Events**:
- When a new order is placed, publish an event to `OrderEventsTopic`:

     ```sh
     aws sns publish --topic-arn arn:aws:sns:us-east-1:123456789012:OrderEventsTopic --message '{ "orderId": "1234", "orderDetails": { ... } }'

6.**Consume and Process Messages**:

- **OrderProcessingQueue**: Service retrieves and processes the order.
- **InventoryUpdateQueue**: Service updates inventory levels.
- **NotificationQueue**: Service sends order confirmation to the customer.

By using this fanout pattern, you ensure that each part of your system can handle its responsibilities independently and efficiently, enhancing scalability and fault tolerance.

Explain how “push notifications” work, using SNS.

SQS and SNS Basics
How might a large scale, distributed application make use of a Queue system like SQS?
A large-scale, distributed application can use Amazon Simple Queue Service (SQS) to:
1.**Decouple Components**: SQS allows different parts of the application to communicate asynchronously, reducing dependencies and improving fault tolerance. For example, a web server can enqueue user requests, which are then processed by backend services independently.
2. **Load Balancing**: By distributing incoming tasks among multiple workers, SQS helps balance the load, ensuring no single component is overwhelmed, thereby enhancing scalability.
3.**Task Buffering**: SQS acts as a buffer to smooth out task spikes, allowing backend systems to process tasks at their own pace, preventing overload during high traffic periods.
4.**Reliable Message Processing**: SQS ensures that messages are not lost and can be retried if processing fails, guaranteeing reliable and durable communication between services.
5.**Parallel Processing**: Multiple consumers can process messages from the queue in parallel, increasing throughput and efficiency for tasks like data processing, logging, and monitoring.
Bookmark and Review
SNS Javascript SDK
SQS Javascript SDK
Reflection
What are your learning goals after reading and reviewing the class README?
After reading and reviewing the class README on AWS Events, my learning goals are clear and focused. I aim to understand and articulate the key differences between SNS (Simple Notification Service) and SQS (Simple Queue Service), along with their respective use cases. Additionally, I want to grasp the concept of FIFO queues and the publisher/subscriber relationship within these services. Practically, I will learn how to create a notification topic that triggers an action and set up a queue that retains messages. Moreover, I am eager to gain hands-on experience by publishing messages with SNS and subscribing to topics, as well as publishing and consuming messages using SQS in Node.js applications.

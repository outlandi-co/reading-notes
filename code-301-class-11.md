# Readings: MongoDB and Mongoose

## Below you will find some reading material, code samples, and some additional

resources that support the topic for this class and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.
Reading
nosql vs sql

## Fill in the chart with five differences between SQL and NoSQL databases

| SQL                           | NoSQL                           |
|-------------------------------|---------------------------------|
| Structured Query Language    | Not Only SQL                   |
| Relational database           | Non-relational database         |
| Uses tables to store data     | Uses various data models (e.g., document, key-value, graph) |
| Supports ACID transactions    | Often sacrifices ACID properties for performance and scalability |
| Schema-based                  | Schema-less or flexible schema  |

## 1. What kind of data is a good fit for an SQL database?

Structured data with well-defined relationships is typically a good fit for an SQL database. This includes data that can be organized into tables with clearly defined columns and rows, where relationships between entities are established using foreign keys.
Examples of data that are well-suited for an SQL database include:

1. **Transactional Data**: Data related to financial transactions, such as sales orders, invoices, and payments, where consistency and data integrity are critical.
2. **Customer Relationship Management (CRM) Data**: Information about customers, including their contact details, purchase history, and interactions with the company, which often involves complex relationships between entities such as customers, orders, and products.
3. **Enterprise Resource Planning (ERP) Data**: Data related to various business processes such as inventory management, supply chain management, and human resources, where data consistency and integrity are essential for effective operations.
4. **Content Management Systems (CMS)**: Structured content such as articles, blog posts, and user-generated content, where metadata such as author, publication date, and category are stored in a relational database to facilitate efficient retrieval and management.
5. **Inventory and Logistics Data**: Information about inventory levels, suppliers, and shipping logistics, where data needs to be organized and managed efficiently to optimize supply chain operations.

In summary, SQL databases are well-suited for managing structured data with clearly defined relationships and where data integrity and consistency are paramount. They excel in scenarios requiring complex querying, transaction support, and ACID compliance.

## 2. Give a real world example

Consider a retail company that operates an online e-commerce platform. The company uses an SQL database to manage various aspects of its business operations. Here's how different types of data are stored in the SQL database:

1. **Customer Data**: The SQL database contains a table named "Customers" where customer information is stored. Each row in the Customers table represents a unique customer, and columns may include attributes such as customer ID, name, email address, shipping address, and phone number.
2. **Product Data**: Another table named "Products" stores information about the products available for sale on the e-commerce platform. Each row in the Products table represents a unique product, and columns may include attributes such as product ID, name, description, price, and inventory quantity.
3. **Order Data**: When a customer makes a purchase, the details of the order are stored in the Orders table. Each row in the Orders table represents a unique order, and columns may include attributes such as order ID, customer ID (foreign key referencing the Customers table), order date, total amount, and shipping status.
4. **Order Line Items**: To represent the products included in each order, the database may include a table named "Order_Line_Items". This table links orders to the products they contain. Each row in the Order_Line_Items table represents a line item within an order and includes attributes such as order ID (foreign key referencing the Orders table), product ID (foreign key referencing the Products table), quantity, and unit price.
5. **Inventory Data**: The company's inventory data, including information about available quantities of each product, is stored in a table named "Inventory". Each row in the Inventory table represents a unique inventory item, and columns may include attributes such as product ID (foreign key referencing the Products table) and quantity on hand.

By organizing data in this structured manner and establishing relationships between tables, the company can efficiently manage its e-commerce operations, including customer management, product catalog management, order processing, and inventory management, using an SQL database.

## 3. What kind of data is a good fit a NoSQL database?

NoSQL databases are well-suited for handling unstructured or semi-structured data, as well as scenarios where flexibility, scalability, and performance are prioritized over strict data consistency and relational integrity. Here are some examples of data types that are a good fit for a NoSQL database:

1. **Document-oriented Data**: NoSQL databases excel at storing and querying document-oriented data, where each document contains key-value pairs or JSON-like structures. This includes data such as:
   - Web content: Blog posts, articles, comments, and user-generated content on websites or blogs.
   - Product catalogs: Information about products, including attributes such as name, description, price, and category.
   - Configuration data: Settings, preferences, and configurations for applications or systems.
2. **Time-series Data**: NoSQL databases are well-suited for storing time-series data, which involves capturing and analyzing data points collected over time. This includes data such as:
   - Sensor data: Measurements from IoT devices, including temperature, humidity, pressure, and location data.
   - Log data: Server logs, application logs, and event logs generated by systems, applications, or devices.
   - Financial market data: Stock prices, currency exchange rates, and trading volumes collected at regular intervals.
3. **Graph Data**: NoSQL databases designed for graph data models are suitable for storing and querying highly interconnected data, such as:
   - Social networks: Relationships between users, posts, comments, likes, and followers in social media platforms.
   - Network topology: Nodes and edges representing devices, connections, and relationships in computer networks.
   - Recommendation systems: Nodes representing users, items, and interactions in recommendation engines.
4. **Key-value Pairs**: NoSQL databases that use a key-value pair data model are ideal for simple data storage and retrieval scenarios, such as:
   - Session management: Storing session tokens, user preferences, and session-related data in web applications.
   - Cache storage: Storing frequently accessed data to improve performance and reduce latency in applications.

Overall, NoSQL databases are suitable for scenarios where the data model is dynamic and evolving, and where horizontal scalability and performance are critical requirements. They provide flexibility in data modeling, scalability, and efficient handling of large volumes of data with diverse structures.

## 4. Give a real world example

A real-world example of data that is a good fit for a NoSQL database is social media data.
Consider a social media platform like Twitter or Instagram, which generates vast amounts of data from user interactions, posts, comments, likes, and shares. This data is inherently unstructured and highly variable, with each post or user profile potentially containing different fields and attributes.
In a NoSQL database, such as MongoDB, this social media data can be stored in collections of JSON-like documents. Each document represents a user profile, a post, a comment, or another type of interaction, and can contain a variety of fields such as user ID, username, timestamp, content, likes, comments, and hashtags.
Here's how social media data might be structured in a NoSQL database:

- **Users Collection**: Contains documents representing user profiles, with fields such as user ID, username, bio, follower count, following count, and profile picture URL.
- **Posts Collection**: Contains documents representing posts made by users, with fields such as post ID, user ID (foreign key referencing the Users collection), timestamp, content, image URL, likes count, and comments array.
- **Comments Collection**: Contains documents representing comments made on posts, with fields such as comment ID, post ID (foreign key referencing the Posts collection), user ID (foreign key referencing the Users collection), timestamp, and content.
- **Likes Collection**: Contains documents representing likes given by users on posts or comments, with fields such as like ID, post ID or comment ID (foreign key referencing the Posts or Comments collection), user ID (foreign key referencing the Users collection), and timestamp.

By storing social media data in a NoSQL database, the social media platform can easily handle the dynamic and unpredictable nature of user-generated content. NoSQL databases allow for flexible data modeling, efficient storage and retrieval of unstructured data, and horizontal scalability to accommodate the platform's growing user base and data volume over time.

## 5. Which type of database is best for hierarchical data storage?

For hierarchical data storage, a NoSQL database known as a document-oriented database is often the best choice. Document-oriented databases are designed to store, retrieve, and manage hierarchical data structures efficiently.
Hierarchical data structures are those where data is organized in a tree-like fashion, with parent-child relationships between entities. Each entity can have one or more children, forming a hierarchical or nested structure.
Document-oriented databases store data in flexible, JSON-like documents, where each document represents a record and can contain nested sub-documents or arrays. This makes them well-suited for representing hierarchical data structures.
One of the most popular document-oriented databases is MongoDB. In MongoDB, hierarchical data can be represented using nested documents or arrays within documents. This allows for the efficient storage and retrieval of hierarchical data without the need for complex joins or foreign key relationships.
For example, consider an organizational chart where each employee has a hierarchical relationship with their manager and subordinates. This hierarchical data can be stored in MongoDB as a collection of documents, where each document represents an employee and contains fields such as employee ID, name, department, and a nested sub-document representing their manager.
Overall, document-oriented databases like MongoDB are the best choice for storing hierarchical data structures due to their flexibility, scalability, and efficient handling of nested data.

## 6. Which type of database is best for scalability?

When it comes to scalability, both SQL and NoSQL databases can be designed for horizontal scaling, but NoSQL databases are often preferred for their inherent scalability features. NoSQL databases are built to handle large volumes of data and high throughput, making them well-suited for scalable applications. Here's why:

1. **Horizontal Scalability**: NoSQL databases are designed to scale horizontally by adding more servers or nodes to a distributed database cluster. This allows them to handle increasing loads and data volumes by distributing data across multiple nodes. SQL databases can also scale horizontally, but it often requires more complex setup and sharding strategies.
2. **Schema Flexibility**: NoSQL databases typically offer more flexibility in data modeling compared to SQL databases. This flexibility makes it easier to adapt the database schema to changing requirements and scale out without needing to modify existing data structures.
3. **Data Distribution**: NoSQL databases use distributed architectures that can automatically partition and distribute data across multiple nodes in a cluster. This enables better load balancing and fault tolerance, ensuring that the database remains available and responsive even under heavy loads.
4. **Performance**: NoSQL databases are optimized for high-performance read and write operations, making them well-suited for scalable applications with demanding performance requirements. They often use techniques such as in-memory caching, asynchronous replication, and optimized storage engines to achieve high throughput and low latency.
5. **Use of Commodity Hardware**: NoSQL databases are designed to run on commodity hardware, allowing organizations to scale out using cost-effective hardware components. This makes it more affordable to expand the database infrastructure as needed to accommodate growth.
Overall, while both SQL and NoSQL databases can be designed for scalability, NoSQL databases are often preferred for their inherent scalability features, flexibility, and performance optimizations, making them the best choice for building scalable applications with high-volume data requirements.

## 1. What does SQL stand for?

SQL stands for Structured Query Language. It is a domain-specific language used in programming and managing relational databases. SQL is commonly used for tasks such as querying data, updating data, defining database schema, and managing access control in relational database management systems (RDBMS).

## 2. What is a relational database?

A relational database is a type of database that organizes data into tables with rows and columns, following the relational model. In a relational database:

1. **Tables**: Data is stored in tables, also called relations. Each table consists of rows (also known as tuples or records) and columns (also known as attributes or fields).
2. **Rows**: Each row represents a single record or instance of data, containing information about a specific entity. For example, in a table of employees, each row might represent one employee, with columns for attributes such as name, employee ID, and department.
3. **Columns**: Columns define the attributes or properties of the entities being stored. Each column has a name and a data type that determines the kind of data it can hold. For example, a column might store text, numbers, dates, or binary data.
4. **Keys**: Relational databases use keys to establish relationships between tables and ensure data integrity. The primary key uniquely identifies each row in a table, while foreign keys establish relationships between tables by referencing primary keys in other tables.

Relational databases are designed to support structured data with well-defined relationships between entities. They provide powerful querying capabilities using Structured Query Language (SQL), enabling users to retrieve, manipulate, and analyze data efficiently. Relational databases are widely used in various applications and industries due to their flexibility, scalability, and robustness.

## 3. What type of structure does a relational database work with?

A relational database works with a tabular structure. This means that data is organized into tables, each of which consists of rows and columns.
Here's a breakdown of the structure:

1. **Tables**: Also known as relations, tables are the fundamental structure in a relational database. Each table represents a distinct entity or concept, such as customers, products, or orders.
2. **Rows**: Each row in a table represents a single record or instance of the entity being modeled. It contains data specific to that instance, with each column representing a different attribute or property of the entity.
3. **Columns**: Columns define the different types of data that can be stored in each row. Each column has a unique name and data type, such as text, numeric, date, or binary.
4. **Keys**: Relational databases use keys to establish relationships between tables and ensure data integrity. Primary keys uniquely identify each row within a table, while foreign keys establish relationships between tables by referencing primary keys in other tables.

Overall, the tabular structure of a relational database provides a logical and organized way to store and manage structured data, enabling efficient querying, manipulation, and analysis of data.

## 4. What is a ‘schema’?

In the context of databases, a "schema" refers to the overall structure or blueprint that defines how data is organized and stored within the database. It encompasses the layout of tables, the relationships between tables, the data types of each column, and any constraints or rules applied to the data.
Here's a breakdown of what a schema typically includes:

1. **Table Definitions**: The schema defines the tables that exist within the database and the columns they contain. Each table is given a name that represents a specific entity or concept, such as "Customers", "Products", or "Orders".
2. **Column Definitions**: For each table, the schema specifies the columns (also known as attributes or fields) that make up the table. Each column is given a name and a data type that determines the type of data it can store, such as text, numeric, date, or binary.
3. **Relationships**: In relational databases, tables are often related to each other through foreign key constraints. The schema defines these relationships, indicating which columns in one table reference the primary key of another table.
4. **Constraints**: Constraints enforce rules and conditions on the data to ensure its integrity and consistency. Common constraints include primary key constraints (ensuring each row has a unique identifier), foreign key constraints (enforcing referential integrity between tables), and data validation rules (e.g., ensuring a column only accepts values within a certain range).

Overall, the schema serves as a blueprint for how data is structured and organized within the database. It provides a framework for developers, administrators, and users to understand the database's structure and how data is related, facilitating data management, querying, and analysis.

## 5. What is a NoSQL database?

A NoSQL database is a type of database that provides a mechanism for storage and retrieval of data modeled in ways other than the tabular relations used in relational databases. NoSQL stands for "Not Only SQL," indicating that these databases may support various data models beyond the traditional SQL-based relational model.
NoSQL databases are designed to address limitations of traditional relational databases, particularly in terms of scalability, flexibility, and performance. They are often used in scenarios where:

1. **Scalability**: NoSQL databases are designed to scale out horizontally across multiple servers or nodes, making them well-suited for handling large volumes of data and high throughput.
2. **Flexibility**: NoSQL databases offer more flexibility in data modeling compared to relational databases. They can handle unstructured, semi-structured, and structured data, allowing for dynamic and evolving data schemas.
3. **Performance**: NoSQL databases are optimized for high-performance read and write operations, making them suitable for applications with demanding performance requirements, such as real-time analytics, content management systems, and IoT platforms.
There are several types of NoSQL databases, each with its own data model:
1.**Document-oriented databases**: Store data as flexible, JSON-like documents, allowing for nested and hierarchical data structures. Examples include MongoDB, Couchbase, and CouchDB.
2.**Key-value stores**: Store data as key-value pairs, where each key is unique and associated with a value. Examples include Redis, Amazon DynamoDB, and Riak.
3.**Column-family stores**: Store data in columns rather than rows, allowing for efficient retrieval of subsets of columns. Examples include Apache Cassandra, HBase, and ScyllaDB.
4.**Graph databases**: Store data in graph structures, consisting of nodes, edges, and properties, allowing for efficient querying of complex relationships. Examples include Neo4j, Amazon Neptune, and ArangoDB.

Overall, NoSQL databases offer flexibility, scalability, and performance advantages over traditional relational databases, making them a popular choice for modern applications dealing with diverse and rapidly changing data requirements.

## 6. How does it work?

A NoSQL database is a type of database that provides a mechanism for storage and retrieval of data modeled in ways other than the tabular relations used in relational databases. NoSQL stands for "Not Only SQL," indicating that these databases may support various data models beyond the traditional SQL-based relational model.
NoSQL databases are designed to address limitations of traditional relational databases, particularly in terms of scalability, flexibility, and performance. They are often used in scenarios where:

1.**Scalability**: NoSQL databases are designed to scale out horizontally across multiple servers or nodes, making them well-suited for handling large volumes of data and high throughput.
2.**Flexibility**: NoSQL databases offer more flexibility in data modeling compared to relational databases. They can handle unstructured, semi-structured, and structured data, allowing for dynamic and evolving data schemas.
3.**Performance**: NoSQL databases are optimized for high-performance read and write operations, making them suitable for applications with demanding performance requirements, such as real-time analytics, content management systems, and IoT platforms.
There are several types of NoSQL databases, each with its own data model:
1.**Document-oriented databases**: Store data as flexible, JSON-like documents, allowing for nested and hierarchical data structures. Examples include MongoDB, Couchbase, and CouchDB.
2.**Key-value stores**: Store data as key-value pairs, where each key is unique and associated with a value. Examples include Redis, Amazon DynamoDB, and Riak.
3.**Column-family stores**: Store data in columns rather than rows, allowing for efficient retrieval of subsets of columns. Examples include Apache Cassandra, HBase, and ScyllaDB.
4.**Graph databases**: Store data in graph structures, consisting of nodes, edges, and properties, allowing for efficient querying of complex relationships. Examples include Neo4j, Amazon Neptune, and ArangoDB.

Overall, NoSQL databases offer flexibility, scalability, and performance advantages over traditional relational databases, making them a popular choice for modern applications dealing with diverse and rapidly changing data requirements.

## 7. What is inside of a MongoDB database?

Inside a MongoDB database, data is stored in a flexible and schema-less format, primarily as JSON-like documents within collections. Here's what you'll typically find inside a MongoDB database:

1. **Collections**: MongoDB organizes data into collections, which are analogous to tables in relational databases. Each collection contains a set of documents, and collections can be thought of as containers for related documents.
2. **Documents**: Documents are the basic unit of data storage in MongoDB. Each document is a JSON-like object that contains key-value pairs of fields and values. Documents can have nested structures, allowing for complex and hierarchical data modeling. In MongoDB, documents within a collection can have different structures, providing flexibility in data modeling.
3. **Fields**: Fields are individual elements within a document that store data. Each field has a name and a corresponding value, which can be of various data types, including strings, numbers, arrays, objects, dates, and binary data.
4. **Indexes**: MongoDB supports indexing to optimize query performance. Indexes can be created on individual fields or combinations of fields within documents. Indexes help MongoDB quickly locate and retrieve documents based on query criteria, improving query performance.
5. **GridFS**: MongoDB includes a feature called GridFS for storing and retrieving large binary files, such as images, videos, and audio files. GridFS stores files as separate documents within collections, allowing for efficient storage and retrieval of large files that exceed the BSON document size limit.
6. **System Collections**: MongoDB includes system collections that store metadata and configuration information about the database and its collections. Examples include the system.namespaces collection, which stores information about namespaces (collections and indexes), and the system.indexes collection, which stores information about indexes.

Overall, MongoDB databases store data in a flexible and scalable manner, using JSON-like documents within collections. This document-oriented approach allows for dynamic and schema-less data modeling, making MongoDB well-suited for a wide range of use cases, including content management, real-time analytics, and mobile application development.

## 8. Which is more flexible - SQL or MongoDB? and why

The flexibility of a database system depends on various factors, including data modeling capabilities, schema enforcement, and support for evolving data structures. Comparing SQL databases and MongoDB (a NoSQL database), both offer different types of flexibility suited to different use cases:

1. **SQL Databases (Relational Databases)**:

   - **Schema Flexibility**: SQL databases typically enforce a rigid schema, requiring predefined table structures with fixed columns and data types. While this can provide data consistency and integrity, it may limit flexibility in adapting to changing data requirements.
   - **Data Relationships**: SQL databases excel at managing relationships between tables through foreign key constraints and join operations. This structured approach ensures relational integrity but may add complexity and restrict flexibility when dealing with complex or evolving data models.
   - **Data Consistency**: SQL databases enforce ACID (Atomicity, Consistency, Isolation, Durability) properties, ensuring data consistency and transactional integrity. This strict consistency model may limit flexibility in certain scenarios where eventual consistency or relaxed transactional requirements are acceptable.

2. **MongoDB (NoSQL Database)**:

   - **Schema Flexibility**: MongoDB offers more flexibility in data modeling compared to SQL databases. It allows for dynamic and schema-less data structures, where documents within collections can have varying structures and fields. This flexibility enables developers to adapt the database schema to evolving data requirements more easily.
   - **Data Relationships**: MongoDB supports embedded documents and arrays, allowing for hierarchical data structures and nested relationships within documents. While it may not enforce strict referential integrity like SQL databases, it provides flexibility in representing complex data models without the need for joins.
   - **Horizontal Scalability**: MongoDB is designed for horizontal scalability, allowing databases to scale out across multiple servers or nodes. This scalability enables MongoDB to handle large volumes of data and high throughput, providing flexibility in accommodating growing workloads.

In summary, MongoDB is often considered more flexible than traditional SQL databases in terms of schema flexibility and adaptation to evolving data structures. However, SQL databases offer strong consistency guarantees and well-defined data relationships, which may be advantageous in certain scenarios. Ultimately, the choice between SQL and MongoDB depends on the specific requirements of the application, including data modeling needs, scalability requirements, and consistency guarantees.

## 9. What is the disadvantage of a NoSQL database?

While NoSQL databases offer many advantages, they also come with some disadvantages, including:

1. **Lack of ACID Transactions**: Many NoSQL databases sacrifice ACID (Atomicity, Consistency, Isolation, Durability) properties in favor of performance and scalability. This means they may not provide the same level of transactional consistency and data integrity as traditional SQL databases, which can be a disadvantage for applications requiring strong consistency guarantees.
2. **Limited Query Capabilities**: NoSQL databases often have less mature query languages and fewer features for complex querying and analytics compared to SQL databases. While they excel at simple key-value lookups or document retrievals, performing complex aggregations, joins, and ad-hoc queries may be more challenging.
3. **Schema Design Complexity**: While NoSQL databases offer schema flexibility, managing complex or evolving data models can be more challenging compared to SQL databases. Without a predefined schema, ensuring data consistency and integrity may require additional application logic or data validation.
4. **Maturity and Ecosystem**: NoSQL databases are often newer and less mature than traditional SQL databases, which may result in a smaller ecosystem of tools, libraries, and community support. This can make it more difficult to find resources, expertise, and third-party integrations for NoSQL databases.
5. **Data Consistency Trade-offs**: NoSQL databases may employ eventual consistency models or relaxed consistency guarantees to achieve high scalability and performance. While this can improve system performance, it may lead to data inconsistency or stale reads in distributed environments, which can be undesirable for certain applications.
6. **Learning Curve**: Transitioning from SQL databases to NoSQL databases may require developers to learn new concepts, query languages, and data modeling techniques. This learning curve can be a disadvantage for teams with extensive experience in SQL-based technologies.
Overall, while NoSQL databases offer many benefits, including scalability, flexibility, and performance, it's essential to consider their limitations and trade-offs when evaluating them for specific use cases. Depending on the requirements of your application, a NoSQL database may or may not be the best fit.

Bookmark and Review
mongoose api
React Router

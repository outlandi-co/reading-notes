# Readings: Data Modeling

Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.
Review the Submission Instructions for guidance on completing and submitting this assignment.
Reading
nosql vs sql

1.**What type of database is the best fit for the complex query intensive environment?**

For a complex query-intensive environment, a relational database like SQL is often the best fit. SQL databases are structured and excel at handling complex queries involving multiple tables and relationships. They ensure data integrity and consistency, making them reliable for demanding query scenarios.

2.**What type of database is the best fit for hierarchical data storage?**

Hierarchical data storage is best managed by a NoSQL database, particularly a document-oriented database like MongoDB. NoSQL databases are flexible and can store hierarchical data structures naturally, without needing to adhere to rigid schemas. This makes them perfect for storing data with nested relationships, such as JSON-like documents.

3.**Describe the differences in scalability between a SQL and NoSQL database as though you were speaking to a non-technical friend.**

 Imagine you're building a house. With a SQL database, it's like building a house with a strong foundation and specific rooms designated for different purposes. As you add more rooms (data), the house needs to be carefully expanded, which takes time and effort. This is because SQL databases have a fixed structure, and scaling them requires adjusting the existing setup.
On the other hand, NoSQL databases are like building with modular blocks. You can add or remove blocks easily, allowing for quicker expansion. Each block can be customized to fit the need, so as your needs grow, you can simply add more blocks without having to redesign the entire structure. This flexibility makes NoSQL databases more scalable, especially for rapidly growing or changing data requirements.

sql modeling techniques

1.**Among data tables, what is a one-to-many relationship and how do we “relate” them?**

Among data tables, a one-to-many relationship refers to a situation where one record in a table can be associated with multiple records in another table, but each record in the second table can only be associated with one record in the first table. To "relate" tables with a one-to-many relationship, you typically establish a foreign key in the "many" side table that references the primary key in the "one" side table. This foreign key establishes the relationship between the two tables.

2.**Prior to designing your relational database, it might be useful to ___ a ___ of the database tables and their relationships.**

Prior to designing your relational database, it might be useful to sketch a diagram of the database tables and their relationships. This helps visualize how different tables are connected and ensures that the relationships between them are correctly established before implementation.

3.**Explain the difference between a primary and foreign key.**

- **Primary Key**: A primary key is a column (or a set of columns) in a table that uniquely identifies each record in that table. It ensures that each row in the table is uniquely identifiable. For example, in a table of customers, the customer ID column might be designated as the primary key. Primary keys are typically indexed for efficient retrieval and enforce data integrity constraints.
- **Foreign Key**: A foreign key is a column (or a set of columns) in a table that establishes a link between data in two tables. It refers to the primary key of another table and is used to enforce referential integrity. In our previous example, the foreign key in the orders table references the primary key in the customers table, creating a relationship between the two tables. Foreign keys help maintain consistency and integrity in the database by ensuring that references between related tables are valid.

Videos
sql vs nosql

1.**How do we treat keywords and parameters differently in SQL syntax?**

In SQL syntax, keywords are reserved words that have predefined meanings in the language. They are used to perform specific actions or operations within SQL statements, such as SELECT, INSERT, UPDATE, and DELETE. Parameters, on the other hand, are values that are passed into SQL statements to customize their behavior. Parameters can be used in queries to filter, sort, or manipulate data dynamically. While keywords are part of the SQL language itself and have fixed meanings, parameters are placeholders for values that can change based on user input or other factors.

2.**Define normalization within the context of schemas and data.**

Normalization is the process of organizing data in a database efficiently by reducing redundancy and dependency. It involves breaking down large tables into smaller, related tables and defining relationships between them. The goal of normalization is to minimize data redundancy and avoid anomalies such as insertion, update, and deletion anomalies, which can lead to inconsistencies in the database. Normalization typically involves several normal forms (e.g., first normal form, second normal form, etc.), each specifying certain criteria that a database schema must meet to be considered normalized.

3.**Explain the difference between one-to-one, one-to-many, and many-to-many relationships to a non-technical recruiter.**

- **One-to-One Relationship**: Imagine you have a company directory where each employee has one and only one desk assigned to them. This is like a one-to-one relationship; each employee corresponds to one desk, and each desk corresponds to one employee. It's a direct, straightforward connection, just like each employee having one desk.

- **One-to-Many Relationship**: Now, picture a scenario where one manager oversees multiple employees in a department. This is a one-to-many relationship; one manager can have many employees reporting to them, but each employee reports to only one manager. It's like a tree structure, where one person (the manager) branches out to several (the employees), but each branch only leads to one person.
- **Many-to-Many Relationship**: Think of a situation where students can enroll in multiple courses, and each course can have multiple students enrolled. This is a many-to-many relationship; many students can be enrolled in many courses, forming a complex web of connections. It's like a network where many nodes (students) are connected to many other nodes (courses), creating a dynamic and interconnected system.

Bookmark and Review
sequelize api
Reflection

1.**What are your learning goals after reading and reviewing the class README?**

I'm feeling a surge of excitement and determination as I dive into the world of databases. The readings I've encountered introduce the concept of data modeling, emphasizing its pivotal role in translating real-world ideas into JavaScript data types. I'm particularly intrigued by the fundamental topics covered, such as CRUD operations, SQL databases, and the Sequelize ORM.

The complexity and diversity of databases fuel my enthusiasm, and I'm eager to unravel their intricacies. The breakdown of SQL shell commands and Sequelize associations in the material is immensely helpful, making database management feel less daunting and reinforcing my belief in its potential to propel me toward my goals.

I'm confident that mastering databases will not only satisfy my curiosity but also open doors to new opportunities in the future. It's an exhilarating journey, and I can't wait to see where it takes me.

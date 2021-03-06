# Entity Framework and APIs

### Razor Pages is an alternative programming model. make coding page-focused scenarios easier and more productive than using controllers and views.

### Entity Framework (EF) Core is a lightweight, extensible, open source and cross-platform version of the popular Entity Framework data access technology.

### Model View Controller (MVC)
MVC is a design pattern used to decouple user-interface (view), data (model), and application logic (controller). This pattern helps to achieve separation of concerns.

Using the MVC pattern for websites, requests are routed to a Controller that is responsible for working with the Model to perform actions and/or retrieve data. The Controller chooses the View to display and provides it with the Model. The View renders the final page, based on the data in the Model.

### Model is made up of entity classes and a context object that represents a session with the database. 

EF supports the following model development approaches

1- Generate a model from an existing database.

2- Hand code a model to match the database.

3- Once a model is created, use EF Migrations to create a database from the model. Migrations allow evolving the database as the model changes.

### Querying Instances of your entity classes are retrieved from the database using Language Integrated Query (LINQ).

### Saving data Data is created, deleted, and modified in the database using instances of your entity classes.

### EF O/RM considerations
While EF Core is good at abstracting many programming details, there are some best practices applicable to any O/RM that help to avoid common pitfalls in production apps

1- Intermediate-level knowledge or higher of the underlying database server is essential to architect, debug, profile, and migrate data in high performance production apps. For example, knowledge of primary and foreign keys, constraints, indexes, normalization, DML and DDL statements, data types, profiling, etc.

2- Functional and integration testing: It's important to replicate the production environment as closely as possible to

  * Find issues in the app that only show up when using a specific versions or edition of the database server.
  * Catch breaking changes when upgrading EF Core and other dependencies. For example, adding or upgrading frameworks like ASP.NET Core, OData, or AutoMapper. These dependencies can affect EF Core in unexpected ways.

3- Performance and stress testing with representative loads. The na??ve usage of some features doesn't scale well. For example, multiple collections Includes, heavy use of lazy loading, conditional queries on non-indexed columns, massive updates and inserts with store-generated values, lack of concurrency handling, large models, inadequate cache policy.

4- Security review: For example, handling of connection strings and other secrets, database permissions for non-deployment operation, input validation for raw SQL, encryption for sensitive data.

5- Make sure logging and diagnostics are sufficient and usable. For example, appropriate logging configuration, query tags, and Application Insights.

### Data seeding is the process of populating a database with an initial set of data.

### Limitations of model seed data

1- Temporary data for testing

2- Data that depends on database state

3- Data that is large (seeding data gets captured in migration snapshots, and large data can quickly lead to huge files and degraded performance).

4- Data that needs key values to be generated by the database, including entities that use alternate keys as the identity

### User secrets is a secure way of storing private user information such as API keys, client secrets, and connection strings.


# SYSTEM DESIGN

### MICROSERVICES

- Microservices is an architectural style and approach to software development where an application is structured as a collection of loosely coupled and independently deployable services. Each service in a microservices architecture focuses on a specific business capability and can be developed, deployed, and scaled independently. These services communicate with each other through well-defined APIs (typically over HTTP or messaging protocols) and can be implemented using different programming languages and technologies.
- Large scale microservices often use multiple databases. This could be a single database with multiple schemas or different physical database servers.
- Incoming requests are handled by an API Gateway and the gateway decides which service to pass the request. API Gateway can handle Authentication and Authorization via an Authentication service (Identity Provider)
- Disadvantages
  - Difficult to debug
  - No data integrity if services are using multiple databases.
  - Not for small teams/companies
  - Communication of each service is done via network (latency and other network related costs)

### API GATEWAY

- An API Gateway is a server that acts as an API front-end to Microservices and forwards all the incoming requests to the appropriate services.
- Authentication and Authorization: They often handle authentication and authorization, ensuring that only authorized users or applications can access specific APIs. This can involve integrating with identity providers, such as OAuth or OpenID Connect.
- Security: API Gateways can enforce security policies such as rate limiting, IP filtering, and request/response validation to protect against attacks like DDoS or injection attacks.
- Can cache the frequently requested data temporarily, reducing the load on back-end services and improving response times.
- Can transform request into an appropriate protocol e.g API Gateway forwards the incoming request to Auth service via gRPC and the response can be transformed into the API gateway public facing protocol (rest api/graphql)
- Logging and Monitoring: They can log API requests and responses, which is essential for debugging and monitoring. They can also provide analytics on API usage.
- Load Balancing: They can distribute incoming requests across multiple instances of a service to ensure high availability and scalability.

### NOSQL DATABASES

- NoSQL databases, often referred to as "Not Only SQL" databases, are a class of database management systems that provide a flexible approach to data storage and retrieval.
- Database Types: Document, Wide-Column, Key-Value, Graph
- Schemaless
- Support horizontal Scaling due to their schemaless nature
- Relationship data can be stored in a NoSQL database it's just modeled differently
- In early years, NoSQL databases were not ACID complaint but now many databases fully support it. Examples of these databases are Mongodb, Neo4j

### PUBLISH SUBSCRIBE PATTERN

The Publisher-Subscriber (Pub-Sub) pattern is a messaging pattern used in software architecture and design to facilitate communication between components or services without requiring them to directly know about each other. It is often used in distributed systems and event-driven architectures. In the Pub-Sub pattern, there are three main components:

- **Publisher:** The publisher is responsible for producing and sending messages (events) to a central message broker or Pub-Sub system. These messages typically contain information about events or changes that have occurred within the publisher's domain.

- **Subscriber:** Subscribers are components or services that express interest in receiving specific types of messages or events. Subscribers subscribe to one or more message channels or topics, indicating the kinds of events they want to receive.

- **Message Broker (or Pub-Sub System):** The message broker acts as an intermediary that receives messages from publishers and routes them to the appropriate subscribers based on the topics or channels they have subscribed to. The broker manages the distribution of messages to subscribers and can often provide additional features like message persistence, filtering, and scalability.

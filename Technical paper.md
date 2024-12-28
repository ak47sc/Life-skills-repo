# REST Architecture Technical Paper
## 1. Introduction
- REST stands for **Representational State Transfer**.
- It is a software architectural style that defines a set of rules for creating web services.
- It follows a uniform and predefined set of rules to access the system and manipulate web resources.
- Restful system consists of:
  - client requesting resources
  - Server providing resources

## 2. Architectural Constraints of RESTful API
It consists of six architectural constraints that make any web service. There are:
- Uniform Interface
- Stateless
- Cacheable
- Client-Server
- Layered System
- Code on Demand

### 2.1 Uniform Interface
- It is a key constraint that makes it unique to non-REST APIs.
- The idea is that there should be a uniform way of interacting with the server irrespective of the application.

There are four main guidelines that need to be followed:
- **Resource-Based** : Resources are uniquely identified by URIs. Example: /api/features, /api/products
- **Manipulation of Resources Through Representations** : Users get a unique representation of the resources and contain sufficient information to modify or delete the resources, provided it has relevant permissions. For example, a user gets a user ID when logged in and can use it to modify or delete its user credentials.
- **Self-descriptive Messages** : Request contains enough information for processing the request.
- **Hypermedia as the Engine of Application State (HATEOAS)** : It needs to include links for each response so that clients can discover other resources easily.

### 2.2 Stateless 
- Stateless means the requests are independent, and the server handles each request separately without any prior knowledge of the client. So the request must contain all the information to fulfill the request.
- It helps to enable greater availability since the server does not have to maintain, update, or communicate that session state.

### 2.3 Cacheable
- Requests are required to announce if it is cacheable or not and their duration it can be cached at the client side. This allows the client to return the data from the cache for any subsequent requests and has no need of sending requests again to the server.
- It helps to improve performance as it reduces some client–server interactions.

### 2.4 Client-Server
- A REST application requires a client-server architecture.
- The client is the one who requires resources, and a server is the one who provides the resources.
  
### 2.5 Layered System
- REST applications are composed of multiple layers without knowing each other except their immediate layer.
- This decouples the client from the backend, enabling scalability and flexibility.
### 2.6 Code on Demand
- The server can send executable code (like JavaScript) to the client, which then can be executed by the client.
- This constraint is optional.

## 3. Common HTTP Methods Used in REST
- **GET** : Retrieves resources from the server and can cache the information. Example: getting a list of products.
- **POST** : Creates a new resource with the information provided in the request, and it is not cacheable.
- **PUT** : Updates an existing resource with an ID specified in the request.
- **DELETE** : Deletes an existing resource specified in the request.

## 4. Some REST API interactions
1. **GET/products** :
   - Retrieves a list of products.
   - Response example :
     ```
       [
         {
           "id":1,
           "name":"coke",
           "price":30
         }
       ,
         {
           "id":2,
           "name":"lays",
           "price":10
         }
      ]
     ```
2. **GET/products/2** :
   - Retrieves product with ID 2.
   - Response example :
     ```
     {
       "id":2,
       "name":"lays",
       "price":10
     }
     ```
3. **POST/products** :
   - Creates a new product by sending a request with the data in the body.
   - Request example :
     ```
     {
       "name":"dairy milk",
       "price":20
     }
     ```
   - Response Example :
     ```
     201 Created
     ```
4. **PUT/products/1** :
   - Updates the product with ID 1.
   - Request example :
     ```
     {
       "name":"dairy milk",
       "price":25
     }
     ```
   - Response Example :
     ```
     200 OK
     ```
5. **DELETE/products/2** :
   - Deletes product with ID 2.
   - Response Example :
     ```
     204 No Content
     ```

## 5. Advantages of REST
- **Scalability**
- **Interoperability**
- **Simplicity**
- **Statelessness**

## 6. Disadvantages of REST
- **Lack of state**
- **Lack of security**
- **Less reliable**
- **Incompatibility with real-time functionality**

## 7. Conclusion
REST provides a scalable, simple, and flexible architectural style for building web services. By adhering to its principles, developers can create APIs that are performant, easy to maintain, and can integrate with other systems. REST has been widely adopted in modern web development for building APIs due to its simplicity and scalability.

# Web Application Layout

Web Applications are purpose-built and vary from site to site. They are typically composed of three categories of layer-type: Web Application Infrastructure, Web Application Components, and Web Application Architecture.

# Web Application Infrastructure

Web Application Infrastructure refers to the relationship between different components, the app itself. and the database server.

There are four model-types for Application Infrastructure:

#### Client-Server

Client-Server models utilize a main server that responds to all clients. These are simple models where the front-end is rendered by the browser on the client, and the back-end is compiled, interpreted, and executed by the server hosting the resources.

#### One Server

The One Server model uses a single server to host the web application and the database it uses. This model holds the highest factor of risk because if the server were to fail or become compromised, all data for the server, database, and the web application with all of it's user data will be vulnerable to exploitation.

#### Many Servers / One Database

In this model, the servers and database are deliberately kept separate. The servers may or may not access the same resources from the database, but they still use the same database. This model is strong in a security sense because it employs segmentation of the network, meaning that the servers do not communicate or share data with each other. This means that if the database becomes compromised, the servers will not and vice versa. 

#### Many Servers / Many Databases

This model is an extension of the previous model, with the added bonus of extra databases. Having more databases enables more redundancy and security, although this extra hardware may need to be managed with the help of load balancers.

### Web Application Components

Web Application Components are the individual components that the application interacts with, falling into the three categories: UI / UX, Client, and Server components. 

A #client is used to render the resources gathered from the server.

A #server provides the responses to the client's requests. There are various server applications such as webservers, Web Application Logic, and Databases.

A #service, or #microservice, enables third-party integrations and integrations for the web application.

A #Function is a serverless solution.

### Web Application Architecture

Web Application Architecture describes all the relationships between the various components. It is divided into a Three Tier Architecture with the use of three layers.

The Presentation layer is where the UI components enable communication that allows for access to resources, which are provided in the form of #HTML, #CSS, and #JavaScript.

The Application layer checks the status of authorization, privileges, and data and ensures the client's requests are processed correctly.

The Data layer works in conjunction with the application layer to determine the location of the stored and accessed data.

### Microservices 

A Microservice falls under Service-Oriented Architecture ( #SOA) and is a solitary component that typically performs a single task. They are #stateless, meaning that they do not store request or response data, so each of these are independent of one another. Microservices depend on interaction with each other, and they are valued for their ability to scale well and work with differing coding languages between different microservices.

#### Serverless

#Serverless systems are based on #cloud technologies from providers like #AWS, #Google, and #Azure. These are hosted within #stateless containers such as #Docker. This allows developers to build and deploy applications without managing the infrastructure they depend on.



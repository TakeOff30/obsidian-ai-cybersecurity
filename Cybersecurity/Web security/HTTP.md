
## What is HTTP?

HTTP, or Hypertext Transfer Protocol, serves as the foundational protocol for transferring data on the World Wide Web. 

It operates on a request-response model, where a client, typically a [[web browser]], sends a request to a server, and the server responds with the requested resource, such as an HTML document, image, or other type of data. Essentially, it's the language that web browsers and [[web servers]] use to communicate, defining the structure and format of messages exchanged between them to enable the delivery of web content.

HTTP is considered a *stateless* protocol because each request made by a client to a server is treated as a completely independent transaction. 
The server doesn't retain any information or "memory" of previous requests from the same client. Each request contains all the information needed for the server to understand and process it, as if it were the first and only interaction. 

This design simplifies the server's operation, as it doesn't need to maintain session information for each client. While this makes the core protocol simple and scalable, it necessitates the use of other mechanisms, such as [[cookies]] or sessions, to implement stateful interactions where a series of related requests are treated as part of a single session.

HTTP resides at the Application Layer, the topmost layer, of the [[ISO OSI model]]. This means it is concerned with the application-specific data and protocols, providing a way for applications to interact over a network. As an application layer protocol, HTTP relies heavily on the Transport Layer for reliable and ordered data delivery, primarily utilizing [[TCP (Transmission Control Protocol)]]. TCP provides a connection-oriented service, ensuring data integrity and guaranteeing that data packets arrive in the correct sequence. Furthermore, HTTP uses [[DNS (Domain Name System)]] to resolve domain names into [[IP (Internet protocol)]] addresses, allowing it to locate the correct server on the network.
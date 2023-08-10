---
layout: post
title: RESTful architecture
description: "Understanding about Disk RAID"
modified: 2023-08-09
tags: [System Design]
categories: [System Design]
---

# RESTful Request-Response

> This is the messaging pattern traditionally used in web services. The messaging procedure used is Request-Response from client to server. Clients always initiate with a request and procedure ends with a response from the server. ​

> There is a clear distinction between the client and the server roles, and there is a predefined sequence of interactions:

- **Client-Side Initiation** : The client initiates communication by sending an HTTP request to a specific resource on the server. The client specifies the HTTP method (such as GET, POST, PUT, DELETE) and the resource's URL.
- **Server-Side Response** : The server processes the client's request and sends back an HTTP response. The response typically contains the requested data or an acknowledgment, along with an appropriate status code.
- **Client Reception** : The client receives the server's HTTP response and acts based on the response data and status code.


> RESTful architecture emphasizes a few key principles, including:

- **Statelessness**: Each request from a client to a server must contain all the information necessary to understand and process the request. The server doesn't store client state between requests.
    - **REST(Representational State Transfer)** is an architectural style for designing networked applications, particularly web services, that relies on a **stateless** and client-server interaction model using HTTP.

- **Resource-Oriented**: Resources (e.g., URLs) are the main entities that clients interact with. Clients can use different HTTP methods to perform operations on these resources.

- **Uniform Interface**: The interactions between clients and servers are standardized, using a consistent set of HTTP methods (GET, POST, PUT, DELETE) and status codes (such as 200 OK, 404 Not Found).

- **Representation**: Data is exchanged between clients and servers in a standardized format, often using JSON or XML.

<!--## gRPC-->
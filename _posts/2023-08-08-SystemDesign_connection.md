---
layout: post
title: Connection-Oriented Message protocol (Websocket/Http)
description: "Understanding about Stateful req/rep message"
modified: 2023-08-08
tags: [System Design]
categories: [System Design]
---


# Connection-Oriented Request-Response with Notifications

> This is the messaging pattern traditionally used where connection-oriented messaging is used between the peers. The most common messaging procedure is Requst-Response (Req/Cfm/Rej) from client to server, but since the there is a connection, the server can also optionally send asynchronous notifications to the clients (Ind)​.

## Websocket / HTTP

> Once the connection is established, both the server and the client can send signals or messages to each other at any time, without a strict predefined order. This means that both sides have equal communication privileges, and they can initiate communication independently.

- **Connection Establishment**: The WebSocket connection is established through an initial HTTP-based handshake.

- **Bidirectional Communication**: Once the connection is established, both the client and the server can send messages or signals to each other independently and in real-time. There's no strict sequence or predefined initiator.

- **Simultaneous Interaction**: The client and server can exchange messages simultaneously, which is particularly useful for real-time updates, live data streams, and interactive applications.

- The WebSocket Protocol: The official specification for the WebSocket protocol by the Internet Engineering Task Force (IETF).

    - [RFC 6455: The WebSocket Protocol](https://tools.ietf.org/html/rfc6455)

- MDN Web Docs - WebSocket: The Mozilla Developer Network (MDN) provides detailed documentation and tutorials on using WebSocket in web development.

    - [MDN Web Docs: WebSocket](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket)

- WebSocket API Specification: The World Wide Web Consortium (W3C) provides an official specification for the WebSocket API, including methods, events, and examples.
    - [W3C WebSocket API Specification](https://www.w3.org/TR/websockets/)

- HTTP Ptotocol: [RFC 7231: Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content](https://datatracker.ietf.org/doc/html/rfc7231)

- Encoding : [json](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/JSON)
    - JSON (JavaScript Object Notation) is a lightweight data interchange format that is commonly used for encoding data in web applications, including WebSocket communication. JSON provides a way to represent structured data in a human-readable and easily parseable format. It is widely used for data serialization and communication between client and server.

- **Stateful** : The connection is maintained as long as both the client and the server keep it open. The state of the connection is maintained throughout the communication session. Both parties can send messages at any time, and the connection remains open until explicitly closed by either the client or the server. The server can keep track of the state of each connected client and maintain context between messages, allowing for more interactive and real-time applications.


<!-- ## gRPC Streaming -->

---
layout: post
title: RPC Message procedure
description: "Remote Procedure Call - Stateful"
modified: 2022-08-11
tags: [System Design]
categories: [System Design]
---

# RPC

## Remote Procedure Call
> The opposite of a RESTful communication style is often referred to as "RPC" or "Remote Procedure Call" communication. RPC is a different approach to designing communication between distributed systems, and it contrasts with the principles of REST in several ways:

- **Stateful Communication**: Unlike REST, where each request is self-contained and stateless, **RPC communication often involves maintaining some form of state between calls.** This can lead to increased complexity and coupling between the client and server.

- **Method-Centric**: RPC focuses on invoking remote methods or procedures on the server. Clients send requests that specify the method to be executed along with the required parameters. This can lead to tight coupling between the client and server.

- **Complex Contracts**: RPC often relies on complex contracts or interfaces that define the methods, parameters, and return types that can be invoked remotely. Changes to these contracts can have a significant impact on both the client and server.

- **Less Emphasis on Resources**: REST places a strong emphasis on resources and their representations, making it a more natural fit for the web where resources can be easily identified by URLs. RPC tends to be more focused on actions or methods.

- **Uniform Interface**: RESTful communication follows a uniform interface, using standard HTTP methods (GET, POST, PUT, DELETE) and status codes. RPC may have a less standardized approach to method invocation and response handling.

- **Caching and Scalability**: REST promotes caching to improve performance, while RPC may have less emphasis on caching due to its stateful nature.

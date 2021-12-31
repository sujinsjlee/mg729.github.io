---
layout: post
title: Authentification - Session vs. Token vs. Cookies? Understanding concept of Stateless and Stateful
description: "Understanding concept of Authentification"
modified: 2022-01-01
tags: [System Design]
categories: [System Design]
---


## Cookies

- Cookies
     - The server can use cookies to manage data about the user in the browser.
- Cookie behavior
     - When you visit a browser, your browser sends a **Request** to the server.
     - The server will respond to the browser.
     - The response contains all data and page information the user was looking for
     - There may also be cookies that you wish to store in your browser
     - From now on, the user saves a cookie in the browser and whenever the user visits the browser, the browser also sends the cookie along with the request.
- Cookie Features
     - Domain specific: Cookies given by YouTube are sent only to YouTube
     - Expiration Data: Cookies are valid according to the period set by the server
     - Cookies can store various information as well as authentication information (ex, website language setting)
     - Automatically sent

## Stateless
- **Stateless** : All requests to the server are handled independently of previous requests.
- No connection between requests
- No memory
- When the process of the request is finished, the server forgets about the user.

## Session
- HTTP has a stateless request / response operation, so we have to tell who we are every time we make a request.
- One way to handle this is **Session**

- Session operation
    - If the user name + password is sent to the server and the password is correct, the server creates the corresponding user record in the session DB.
    - The session has a unique ID. The session ID is saved and returned to the browser via a cookie.
    - So, when you navigate to another page on the same website, the browser will send a cookie with the session ID to the server.
    - The server checks the session ID attached to the cookie in the request and checks the ID in the session DB
    - From there, it knows that the ID is for a specific User, and then the server knows the user.
    - That is, all important information is on the server side.
    - User has only Session ID
    - Cookie is a medium for passing Session ID
    - Cookie is for browser
    - In native apps, use tokens instead of cookies

- Session Features
    - All session IDs of currently logged in users should be stored in the DB
    - As the number of users increases, the DB should also grow -> **Redis** (a fast and cheap DB to fulfill the purpose)
    
## Token
- String type
- Send Token to server
- The server finds the user matching the corresponding token in the session DB.

## JWT
> User authentication without DB


- Token format
- If user authentication is processed with JWT, there is no need to have a session DB
- Sign the information instead of storing it in the DB and pass it back to the USer

- Afterwards, when the user makes a request to the server, the corresponding 'Signed Info' or 'token' is sent to the server as a request.
- When requesting a page, the server verifies that the token is valid

- No DB management
- Impossible to encrypt (Data with high security should not be managed with JWT)



## Authentification
> [Nomad Coder - Session? Token? Cookies?](https://www.youtube.com/watch?v=tosLBcAX1vk)  
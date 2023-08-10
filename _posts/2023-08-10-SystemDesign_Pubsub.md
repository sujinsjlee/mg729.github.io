---
layout: post
title: PubSub architecture
description: "Understanding about Publish subscribe message protocol"
modified: 2023-08-10
tags: [System Design]
categories: [System Design]
---

# Publish-subscribe

> In this messaging pattern Subscribers subscribe to Topics and Publishers publish messages on Topics. Usually there is a broker involved that broadcasts the message to all Subscribers that have subscribed to the Topic. In this way, Publishers are decoupled from Subscribers.​

## Redis​
> Redis acts as a broker so there are performance penalties compared to brokerless solutions, but it is a high performance, low footprint broker​

> In implementations with a broker there is an extra hop in the broker that can have an impact on performance for message intensive use cases. The extra hop will also impact latency that needs to be considered for use cases with requirements on latency. Redis feature key-space notification is an add-on to Redis Publish-Subscribe. With Key-space notifications the Subscribers subscribes to changes in the key-value database. When the Publisher updates the key-value database a notification is sent by Redis to the Subscribers that have subscribed to that Topic. Key-space notifications is an optional feature in Redis since enabling it have impact on performance. Redis Streams is an append-only data structure that models a log. Publishers append messages to the stream and Subscribers reads messages from the stream. As Redis streams models a log, Subscribers can read old entries from the stream in contrast to Redis Publish-Subscribes where the messages are sent in a fire-and-forget way. Redis Streams also have the Consumer Group concept that allows a group of clients to cooperate to consume a different portion of the same stream of messages.

- Publish-subscribe​
- Key-space notification​
- Streams​

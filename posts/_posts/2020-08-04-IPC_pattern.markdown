---
title: Inter-Process Communication - Microservices
description: architecture,ipc,inter-process,communication,pattern,microservices
---

Inter-process communication (IPC) refers to the mechanisms that allow processes (programs or tasks running on a computer) to communicate with one another. In a microservices architecture, IPC is used to enable communication between the various microservices that make up the system.

There are several different mechanisms that can be used for IPC in a microservices architecture, including:

1. RESTful APIs: One of the most common approaches for IPC in a microservices architecture is to use RESTful APIs. In this approach, microservices expose a set of endpoints that other microservices can call using HTTP requests.

2. Messaging systems: Another common approach for IPC in microservices is to use a messaging system, such as Kafka or RabbitMQ. In this approach, microservices send and receive messages to and from a message broker, which acts as a central hub for communication.

3. RPC frameworks: Remote procedure call (RPC) frameworks, such as gRPC or Thrift, can also be used for IPC in microservices. In this approach, microservices expose a set of functions that can be called by other microservices over the network.

It is important to carefully consider the appropriate IPC mechanism for a microservices architecture, as the choice can have significant implications for the overall performance, reliability, and scalability of the system.

Articles:

* [Inter-Process Communication in a Microservices Architecture](https://dzone.com/articles/building-microservices-inter-process-communication-2)

* [Chapter 3. Interprocess communication in a microservice architecture](https://livebook.manning.com/book/microservices-patterns/chapter-3/1)

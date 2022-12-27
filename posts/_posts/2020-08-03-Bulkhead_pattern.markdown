---
title: Bulkhead pattern - Microservices
description: architecture,bulkhead,pattern,microservices
---

The bulkhead pattern is a software design pattern that is used to improve the resilience and fault tolerance of a system by isolating components or resources. In the context of a microservices architecture, the bulkhead pattern can be used to prevent failures in one service from cascading and affecting other services.

The bulkhead pattern is typically implemented by creating separate resource pools for different components or services, and then setting limits on the number of resources that each pool can consume. This helps to prevent a single component or service from monopolizing resources and potentially causing a failure.

For example, consider a system with three microservices: A, B, and C. If microservice A experiences a high volume of traffic and consumes all of the available CPU resources, it could cause microservices B and C to become unresponsive or to fail. By implementing the bulkhead pattern and allocating a fixed number of CPU resources to each microservice, it is possible to prevent this type of failure from occurring.

The bulkhead pattern is often used in conjunction with other patterns, such as the circuit breaker pattern, to further improve the resilience and fault tolerance of a system.

[Bulkhead pattern](https://docs.microsoft.com/en-us/azure/architecture/patterns/bulkhead "Bulkhead pattern")

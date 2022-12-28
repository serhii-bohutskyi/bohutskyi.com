---
title: Load Balancing Algorithms
description: load,balancer,balancing,algorithm
---


Load balancers distribute traffic among multiple backend servers.
If one of those servers goes down, a load balancer will redirect traffic
to the others, assuring that your services continue to be available.
A load balancer also allows you to add additional resources to handle a
temporary traffic spike or a more consistent increase in demand.
Load balancing aims to optimize resource use, maximize throughput,
minimize response time, and avoid overload of any single resource.

## Load Balancing Algorithms

Different load balancing algorithms provide different benefits;
the choice of load balancing method depends on your needs:

* Round Robin – Requests are distributed across the group of servers sequentially.

* Least Connections – A new request is sent to the server with the
fewest current connections to clients. The relative computing capacity
of each server is factored into determining which one has the least connections.

* IP Hash – The IP address of the client is used to determine which server receives the request.
---

![]({{site.baseurl}}/images/load_balancing.png)
---

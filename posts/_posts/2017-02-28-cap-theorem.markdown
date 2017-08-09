---
title: CAP Theorem
description: CAP theorem,Consistency,Availability,Partition Tolerance,distributed system
---

## CAP - Consistency, Availability, Partition Tolerance

The CAP theorem states that, in a distributed system, you can only have two out of the following three guarantees across a write/read pair: Consistency, Availability, and Partition Tolerance - one of them must be sacrificed.
* Consistency - A read is guaranteed to return the most recent write for a given client.
* Availability - A non-failing node will return a reasonable response within a reasonable amount of time (no error or timeout).
* Partition Tolerance - The system will continue to function when network partitions occur.

![]({{ site.baseurl }}/images/cap-theorem-diagram1.png)

### CAP in NoSQL
![]({{ site.baseurl }}/images/cap-theorem-diagram2.png)
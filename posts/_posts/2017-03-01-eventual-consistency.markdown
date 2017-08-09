---
title: Eventual consistency
description: eventual,consistency,distributed,application,ack,availability,scalability
---

A distributed system maintains copies of its data on multiple machines in order to provide high availability and scalability.
When an application makes a change to a data item on one machine, that change has to be propagated to the other replicas.
Since the change propagation is not instantaneous, there’s an interval of time during which some of the copies will have the most recent change, but others won’t.
In other words, the copies will be mutually inconsistent. However, the change will eventually be propagated to all the copies, and hence the term “eventual consistency”.
The term eventual consistency is simply an acknowledgement that there is an unbounded delay in propagating a change made on one machine to all the other copies.
Eventual consistency is not meaningful or relevant in centralized (single copy) systems since there’s no need for propagation.

When choosing a NoSQL system, it is important to understand whether a choice of consistency policy is available.
If the database system only supports eventual consistency, then the application will need to handle the possibility of reading stale (inconsistent) data.
This is not as easy as it sounds since the responsibility of avoiding the “stale read” problem associated with eventual consistency is left to the application developer.


![]({{ site.baseurl}}/images/eventual-consistency.png)
---
title: Availability Tactics
description: architecture,availability,tactics
---

**Availability tactics** are strategies and techniques that are used to improve the availability of a system. 
The goal of availability tactics is to ensure that a **system** is able to **meet** the required **level** of **uptime** and **performance**, 
even in the face of failures or disruptions.

There are several different **tactics** that can be used to **improve** availability, including:

1. **Redundancy**: Redundancy refers to the use of **multiple copies** of a component or resource to ensure that the system 
can continue to function if one copy fails. This can include **redundant** servers, storage, networking equipment, and other **components**.

2. **Load balancing**: Load balancing is a technique that is used to **distribute** incoming **traffic** evenly across multiple 
servers or **components**, in order to prevent any one server or component from becoming **overloaded**.

3. **Monitoring**: Monitoring is the process of continuously **checking** the health and performance of a system and **alerting** 
administrators if any issues are **detected**. This can help to **identify** problems early and take corrective action before 
they **impact** the availability of the system.

4. **Disaster recovery**: Disaster recovery is the process of **planning** and **preparing** for the possibility of a catastrophic 
event, such as a natural **disaster** or cyber **attack**, and ensuring that the system can be quickly **restored** if such an event occurs.

How to calculate **availability**:

#### a = MTBF/(MTBF MTTR)


* **MTBF** refers to the mean time between failures.
* **MTTR** refers to the mean time to repair.

The term **high availability** typically refers to designs targeting availability of **99.999%** (“5
nines”) or greater. 

![System Availability Requirements]({{site.baseurl}}/images/availability_table.png)

### All availability tactics
![Availability Tactics Diagram]({{site.baseurl}}/images/Availability__Tactics.png)

[Realizing and Refining Architectural Tactics: Availability](https://resources.sei.cmu.edu/asset_files/TechnicalReport/2009_005_001_15101.pdf "Realizing and Refining Architectural Tactics: Availability")

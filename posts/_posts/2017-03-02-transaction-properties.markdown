---
title: Transaction properties - ACID
description: transaction,acid,atomicity,constistency,isolation,durability
---

**ACID** (atomicity, consistency, isolation, and durability) is an acronym
primary attributes ensured to any transaction by a transaction manager
(which is also called a transaction monitor) or simplifying is a set of
properties of database transactions.

* **Atomicity**. In a transaction involving two or more discrete pieces of information,
either all of the pieces are committed or none are.

* **Consistency**. A transaction either creates a new and valid state of data,
or, if any failure occurs, returns all data to its state before the transaction was started.

* **Isolation**. A transaction in process and not yet committed must remain
isolated from any other transaction.

* **Durability**. Committed data is saved by the system such that, even in
the event of a failure and system restart, the data is available in its correct state.

The ACID concept is described in ISO/IEC 10026-1:1992 Section 4.
Each of these attributes can be measured against a benchmark. In general,
however, a transaction manager or monitor is designed to realize the ACID concept.
In a distributed system, one way to achieve ACID is to use a two-phase commit (2PC),
which ensures that all involved sites must commit to transaction completion or none do,
and the transaction is rolled back.


---

![]({{site.baseurl}}/images/acid.png)

---


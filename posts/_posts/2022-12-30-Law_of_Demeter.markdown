---
title: The Law of Demeter
description: software,engineering,principle,the law of demeter,object-oriented,programming,immediate,dependency
---

**The Law of Demeter (LoD)** is a software engineering principle that states that an object should only communicate with its
immediate neighbors and should not have knowledge of the inner workings of other objects. 
The principle is named after the Greek goddess Demeter, who was the goddess of agriculture and fertility.

The Law of Demeter is often applied in object-oriented programming to reduce the complexity and coupling of software systems.
By following the principle, developers can create modular and cohesive code that is easier to understand, maintain, and evolve over time.

---
![]({{site.baseurl}}/images/law_of_demeter.png)

---

The Law of Demeter is often summarized as "only talk to your immediate neighbors." This means that an object should only 
send messages to its direct dependencies and should not have knowledge of the inner workings of other objects or systems. 
By following this principle, developers can create code that is more modular and easier to understand and maintain.

There are several benefits to following the Law of Demeter in software development, including:

##### Improved maintainability
Code that follows the Law of Demeter is typically easier to understand and maintain because it is more modular and cohesive.

##### Reduced complexity 
By limiting the number of dependencies and the amount of knowledge that an object has about other objects, 
developers can reduce the complexity of their code.

##### Improved scalability
Code that follows the Law of Demeter is typically easier to scale because it is more modular and has fewer dependencies.

##### Improved testability
Code that follows the Law of Demeter is typically easier to test because it is more modular and has fewer dependencies.
---
title: S.O.L.I.D principles
description: solid,principle,single,responsibility,open,closed,liskov,interface,dependency
---

The S.O.L.I.D principles of Object Oriented Design(OOD) include these five principles.

Lets expanded the acronyms:

* S - Single-responsibility principle

* O - Open-closed principle

* L - Liskov substitution principle

* I - Interface segregation principle

* D - Dependency inversion principle

## Single-responsibility principle (S.R.P)

A class should have only one job. One and only one reason to change.

Examples of responsibilities :
* Persistence
* Validation
* Notification
* Error Handling
* Logging
* Formatting
* Parsing
* Mapping

## Open-closed principle (O.C.P)

A class should be **open** for extension, but closed for modification.

## Liskov substitution principle (L.S.P)

Subtypes must be substitutable for their base types.

![]({{site.baseurl}}/images/LiskovSubtitutionPrinciple.jpg)

In mathematics, a Square is a Rectangle. Indeed it is a specialization
of a rectangle. The "is a" makes you want to model this with inheritance.
However if in code you made Square derive from Rectangle, then a Square
should be usable anywhere you expect a Rectangle. This makes for some strange behavior.

Imagine you had SetWidth and SetHeight methods on your Rectangle base
class; this seems perfectly logical. However if your Rectangle reference
pointed to a Square, then SetWidth and SetHeight doesn't make sense because
setting one would change the other to match it. In this case Square fails
the Liskov Substitution Test with Rectangle and the abstraction of having
Square inherit from Rectangle is a bad one.

## Interface segregation principle (I.S.P)

Clients should not be forced to depend on methods that they do not use.
Split interface to much smaller regarding S.R.P. to avoid this problem.

## Dependency inversion principle (D.I.P)

High level modules should NOT depend on low level modules, both should
depend on abstractions. Abstractions should NOT depend on details. Details
should depend upon abstractions.

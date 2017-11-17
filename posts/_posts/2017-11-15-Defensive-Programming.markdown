---
title: Defensive Programming Practice
description: defensive,programming,practice
---

# Defensive Programming

Defensive programming is a practice which is designed to ensure code correctness
and reduce number of bugs and failures.

To follow Defensive Programming you need to have a kind of coding policy.
In this article I will add my notes and vision of java defensive programming.

### NullPointerException

Don't be paranoiac, by usage of a checking for **null** everywhere.
Just use a rule "Never return a null" in your system and you will not have problems.

### IllegalArgumentException

If a method is publicly available or receives a input from the outside world,
enforce some defensive measures like **IllegalArgumentException**.

### Put a known object first

It’s just never a bad idea to prevent a random **NullPointerException**
by putting a known object on the left side of an equals().

````java
if ("literal".equals(variable)) { ... }
````

### Always throw on switch default

So many time I saw then somebody has added a new enum item and didn't modify
 switches which handle a logic by those enums.

````java
switch (animal) {
    case CAT: foo(); break;
    case DOG: bar(); break;
    default:
        throw new ThreadDeath("That'll teach you");
}
````


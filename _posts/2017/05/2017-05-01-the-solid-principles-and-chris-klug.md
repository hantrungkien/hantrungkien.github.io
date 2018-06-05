---
layout: post
title: The SOLID Principles (and Chris Klug's take on it)
category: Programming
tags: [Programming, SOLID Principles, Robert Martin, Micheal Feathers, Chris Klug, OOP, OOD, TDD]
date: 2017-05-01 01:30:00 PM UTC
---

<!-- May 1, 2017 09:30:00 PM Philippine Time -->

## [SOLID](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design))

* S – Single Responsibility Principle (SRP)
* O – Open/Closed Principle (OCP)
* L – Liskov Substitution Principle (LSP)
* I – Interface Segregation Principle (ISP)
* D – Dependency Inversion Principle (DIP)

Only last year did I become aware of the importance of the SOLID (or [SDOLI](https://www.hanselman.com/blog/HanselminutesPodcast145SOLIDPrinciplesWithUncleBobRobertCMartin.aspx)) Principles. I heard about these principles many years ago when I was just beginning my career as a software developer but I did not give much time understanding them. I concentrated instead on learning about frameworks and technologies which Uncle Bob calls _"the details"_ instead of the center of our application.

<!--more-->

The SOLID Principles came from Uncle Bob Martin's [series of articles](http://butunclebob.com/ArticleS.UncleBob.PrinciplesOfOod) that were written during the mid 90s.

The original order, _if we follow the dates the papers were written_, was OLDIS. But Micheal Feathers pointed out to Uncle Bob that if he rearranged the letters they can become SOLID. _Then SOLID was born!_

## Uncle Bob Martin's talk on SOLID

The youtube video below is one of Uncle Bob Martin's talks on SOLID that I watched about a month ago: ["S.O.L.I.D principles by Robert C. Martin, popularly known as Uncle Bob at REV3 in Naperville IL"](https://youtu.be/oar-T2KovwE?list=PLC9xJAJbCB0s7BFxKtFDwQZb3IxEUjzT7)

I learned so much from that video. I believe that you will learn so much too! :blush:

<iframe width="560" height="315" src="https://www.youtube.com/embed/oar-T2KovwE?list=PLC9xJAJbCB0s7BFxKtFDwQZb3IxEUjzT7" frameborder="0" allowfullscreen></iframe>


---

## Chris Klug's talk on SOLID

Another video that I watched recently is [Applying SOLID Principles in .NET/C# by Chris Klug - TechEd North America 2014](https://youtu.be/gwIS9cZlrhk)

<iframe width="560" height="315" src="https://www.youtube.com/embed/noxI59PIMyQ" frameborder="0" allowfullscreen></iframe>

I took some notes on the parts about OCP and LSP because I think they are very interesting!

<small>(at about 18:00 mins through the video)</small>

**Open/Closed Principle**

> Once a class is done, it is done.

<small>(at about 19:00)</small>

**He said something about the relationship of TDD and OCP.**

> ... [about] not modifying existing unit tests because we are not going to modify existing classes when we add functionality to the application; we are going to create a new class then create new unit tests for that new class.

_(Wow! That is one of the answers to the "TDD is dead" hype!)_

**Meyer vs. Polymorphic**

> Once a class is done it should not be changed unless there is a bug in it.


<small>(30:30)</small>

**Liskov Substitution Principle**

> A subclass should behave in such a way that it will not cause problems when used instead of the superclass.

**Rules in LSP**

1. Contravariance of arguments...
2. Covariance of return types...
3. No new exception types are allowed to be thrown unless they are subclasses of previously used ones.
- Because the classes that uses your base class might crash if you substitute a subtype of that base class.
4. Preconditions cannot be strengthened in a subtype.
- You should not be expecting things that was not expected in the bass class
5. Postconditions cannot be weakened in a subtype.
- You cannot make changes to the subclass that makes it not do the things it could do before.
- You should not be throwing not implemented exceptions
6. The history constraint
-  You cannot make an immutable class mutable. 
- You cannot make an immutable property in a base class mutable in the derived class.

<small>(36:00)</small>

**LSP General guideline/rule**

> You are not allowed to change a class in a way that you can break any existing applications.

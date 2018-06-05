---
layout: page
title: '"Separate the Business Rules" Quotes'
permalink: /memorabilia/quotes/separate-the-business-rules/
published: false
---

It is called _"high-level policy"_ by Uncle Bob Martin.

It is called just _"policy"_ (vs. mechanisms) by Eddie Bush.

It is called _"business logic"_ by others.

... called _"business rules"_ by others.


_What is so important about this "business rules" thing huh??..._



## Policy, Mechanism, And The Preservation Of Business Value of Eddie Bush


> **The business value in our applications is represented by the policy.** Policy may change over time, and new policies may be introduced, but – if separation of policy and mechanism is followed faithfully – its value can be longer lasting than any user interface or persistence mechanism ever thought about.
<br /><br />
Some policies may change. New policies may come along. However, there are going to be some policies that continue to exist – for very long periods of time – without change. Maybe more than you think.


> Simple applications are the first place you should begin practicing the separation of policy and mechanism because they’re simple. Once they have that formality applied, they can be great testbeds for new UI and persistence frameworks.
<br /><br />
Because of the separation, the work to test these new things out will be super-focused. You’ll truly be able to focus on one thing.


> When policy and mechanism are separated, each thing can be estimated and developed independently. So, you could, for example, make a true business argument for changing from one web framework to another or one persistence mechanism to another.





## Framework Bound[2] of Uncle Bob Martin

Over the years, I’ve adopted a healthy skepticism about frameworks. While I acknowledge that they can be extremely useful, and save a boatload of time; I also realize that there are costs. Sometimes those costs can mount very high indeed.

So my strategy is to keep frameworks like Spring, Hibernate, and Rails at arm’s length; behind architectural boundaries. I get most of the benefit from them that way; and I can take ruthless advantage of them.

But I don’t let those frameworks get too close. I surrender none of my autonomy to them. I don’t allow the tendrils of their code to intermingle with the high level policy of my systems. They can touch my peripheral subsystems; but I keep them away from the core business logic. **The high level policies of my systems shall never be touched by frameworks.**




## from Codesmith's Delight or Terence McGhee



As Robert C. Martin put it, these are the five core characteristics of a decoupled architecture:

Independent of Frameworks. The architecture does not depend on the existence of some library of feature laden software. This allows you to use such frameworks as tools, rather than having to cram your system into their limited constraints.

Testable. The business rules can be tested without the UI, Database, Web Server, or any other external element.

Independent of UI. The UI can change easily, without changing the rest of the system. A Web UI could be replaced with a console UI, for example, without changing the business rules.

Independent of Database. You can swap out Oracle or SQL Server, for Mongo, BigTable, CouchDB, or something else. Your business rules are not bound to the database.

Independent of any external agency. In fact your business rules simply don’t know anything at all about the outside world.


## From isolation article of Mark Seemann



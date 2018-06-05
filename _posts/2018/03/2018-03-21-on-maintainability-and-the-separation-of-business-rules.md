---
layout: post
title: On maintainability and the separation of the business rules
categories: [Programming]
tags: [Clean Architecture, Robert Martin, Terence McGhee, Eddie Bush, Mark Seemann, Woody Zuill]
date: 2018-03-21 11:30:00 PM UTC
---

<!-- January 22, 2018 -->

> "The value of another's experience is to give us hope, not to tell us how or whether to proceed." 
<br /><br />
--- Peter Block (through Woody Zuill in his [talk on mob programming.](https://www.youtube.com/watch?v=sLEsWB1wZMA))

_Story time!..._

During college, I became interested about solving algorithmic problems. But because of lack of mentorship and my lack of knowledge in higher maths and algorithms, I decided to concentrate my energies into studying how to create [line-of-business (LOB) applications](https://blogs.msdn.microsoft.com/dragoman/2007/07/19/what-is-a-lob-application/) (or what is called _"representational-transactional systems"_ [here](https://aryehoffman.com/entry/classifying-software/)).

I thought to myself that creating LOB applications is much easier to do --- it does not require lots of knowledge in maths --- and I thought that I can easily get jobs in the future if I concentrate on creating LOB apps rather than solving algorithmic problems.

During those times, I was curious about how people structure their code in real-world projects.

<!--more-->

I found out about this 3-Layers Architecture thing: you have a **_Presentation Layer_**, **_Business Logic Layer_ (BLL)**, and **_Data Access Layer_ (DAL)**.

I understood what a _Data Access Layer_ is... because during college, _everybody_ knows about databases --- we were kind of [_brainwashed_ :laughing: into thinking that the database is the center of our application](http://blog.cleancoder.com/uncle-bob/2012/05/15/NODB.html). Creating relational data models was the first thing we do when creating software projects during those times.

Also, I understood what a _Presentation Layer_ is --- it has something to do with the UI.

_But, "what is this business logic thing??"..._

_"Hmmm..."_

I did not yet understand what it was during that time.

I also learned that if the app is very simple, one can choose to have _two_ layers only: a **_Data Layer_** and an **_Application Layer_**.

This 2-Layers thing is much easier to comprehend! I know what a _Data Layer_ is... _"Anything that does not involve SQL must be part of the Application Layer!!"_

Great!

So I followed this 2-Layers model in my projects during that time.

A few years later, I came to understand that the validation of user inputs is part of the Business Logic Layer.

So I used that knowledge in one project. I created a separate module for the BLL and then placed my input validations in there.

That was my first experience on separating the business rules from the other parts of a software system.

[_Then the web happened!..._](https://youtu.be/0oGpWmS0aYQ?t=954) I mean, I realized that I need to know how to create web applications.

I started thinking in [monoliths](https://en.wikipedia.org/wiki/Monolithic_application) again.

Luckily I found a job. And after a few months in that job, [DDD](https://en.wikipedia.org/wiki/Domain-driven_design) was introduced to us, the junior developers. Our employer gave us some articles to read about DDD becase we will be involved in an in-house project where concepts from DDD will be used.
<!-- 
That was my introduction to DDD.

I really liked the idea of using the Ubiquitous Language in our code, because you know, _"naming things"_ is one of the hardest things to do in programming. The Ubiquitous Language thing can greatly help on this problem.

I also liked this idea of tight collaboration between the programmers and the business people to produce the right product.

Also, the idea of bounded contexts... it makes things easier to manage. (I heard some say that this idea is similar to this _microservices_ thing).

And, most important of all (at least during my early years as a programmer), I had another thing to google for when deciding on how to structure my projects --- [_"How do I structure a DDD prroject?"_](https://www.google.com.ph/search?q=How+do+I+structure+a+DDD+prroject)
 -->

This gave me another thing to google for when deciding on how to structure my projects --- [_"How do I structure a DDD prroject?"_](https://www.google.com.ph/search?q=How+do+I+structure+a+DDD+prroject)

Then... came... Uncle Bob Martin... with his [charismatic presentations of **_Clean Architecture!_**](2017-04-15-agility-and-architecture-by-uncle-bob-martin-oop-2015-keynote)

He suggests _(preaches even)_ that we keep our _business rules_ separate from the UI, from the database, from the web! And he gave a [sample diagram on how to do it.](/images/2017/CleanArchitectureDesignByUncleBobMartin.png) You can know more about this diagram in the links I will give below.

This is what I call **_my enlightnment_** on how to structure software projects so that they will be maintainable --- in my understanding, you just **make sure that the _business rules_ do not rely on things it should not rely on**, such as the I/O devices... that's it.

Whew!

_Okay... End of story._

That was just a very long introduction to the following list of materials and quotes from our masters, which emphasizes the importance of separating the business rules from the other parts of a software system so that they will be maintainable:


## Some great materials about separating the business rules

### 1. ["A Little Architecture"](http://blog.cleancoder.com/uncle-bob/2016/01/04/ALittleArchitecture.html) of Uncle Bob Martin

> "The business rules should **not know** what specific database you are using."

Uncle Bob gives here an example on how to decouple the business rules from Input/Output things, such as the database.


### 2. ["Clean Architecture"](http://blog.cleancoder.com/uncle-bob/2011/11/22/Clean-Architecture.html) of Uncle Bob Martin

> "No matter how large any one part of the system is, the other parts should be **decoupled** from it."


### 3. ["The Clean Architecture"](http://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html) of Uncle Bob Martin

> "The overriding rule that makes this architecture work is **The Dependency Rule**. This rule says that source code dependencies can only point **inwards**. Nothing in an inner circle can know anything at all about something in an outer circle."


### 4. ["Agility and Architecture" (OOP 2015 Keynote)](https://www.youtube.com/watch?v=0oGpWmS0aYQ) of Uncle Bob Martin

> "The web is not an architecture. **The web is an I/O device**. And we learned many years ago that we want to be independent of I/O devices"

> "**The database is not the center of our system**. Our application should rule the database... The database is also an I/O device; something we want to be independent of."

Uncle Bob has lots of other talks such as ["Architecture: The Lost Years"](https://www.youtube.com/watch?v=Nsjsiz2A9mg). Google for them.


### 5. ["Policy, Mechanism, And The Preservation Of Business Value"](http://craftsmanshipcounts.com/policy-mechanism-preservation-business-value/) of Eddie Bush

> "**The business value in our applications is represented by the policy [or business rules].** Policy may change over time, and new policies may be introduced, but --- if separation of policy and mechanism is followed faithfully --- its value can be longer lasting than any user interface or persistence mechanism ever thought about."

> "Let’s face it, developers want to work on contemporary technologies. **If you’re not separating policy and mechanism, it’s inevitable that you will find yourself in a less favorable position when it comes to recruiting top talent.**"

> "**Don’t Ignore Simple Applications**
 > <br /><br />
> "Simple applications are the first place you should begin practicing the separation of policy and mechanism because they’re simple. Once they have that formality applied, they can be great testbeds for new UI and persistence frameworks."

### 6. ["This Is How We Do It"](https://terencemcghee.com/Articles/Tech/2015/10/25/A0B2606228759D1A888E0AFFDB9DADE0.html) of Terence McGhee

> "One of the most important things that you can learn from me or from anyone else regarding professional software creation, is that you must build your systems for **easy maintainability**."

And separating the business rules from the other parts of a software system is very important to achieve maintainability.

### 7. ["Codesmith's Delight"](https://terencemcghee.com/Articles/Tech/2016/10/15/551B3828CD47198C7C5A58903228DA71.html) of Terence McGhee

> "The primary value of software is that it not only meets today’s needs for today’s users, but that it can **continue** to meet the future needs of all of its users."

### 8. ["Reasons For Isolation"](https://blogs.msdn.microsoft.com/ploeh/2007/05/30/reasons-for-isolation/) of Mark Seeman

He listed here three reasons why we should separate things that need to be separated in our software systems.

### 9. ["Is Layering Worth the Mapping?"](http://blog.ploeh.dk/2012/02/09/IsLayeringWorththeMapping/) of Mark Seeman

Mark Seemann gives here an example of how to separate things in a software system.

He also said that separation is an "all-or-nothing proposition"

> "... the point of the post is that as soon as you soften separation of concerns just a bit, it becomes impossible to maintain that separation. It's an all-or-nothing proposition. Either you maintain strict separation, or you'd be building a monolithic application whether you know it or not."

And remember what Eddie Bush said above: **_"Don’t Ignore Simple Applications... Simple applications are the first place you should begin practicing..."_**

Happy coding!!!

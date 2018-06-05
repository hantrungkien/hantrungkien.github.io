---
layout: post
title: A better way than OO!... and TDD?
categories: [Programming]
tags: [Mark Seemann, Robert Martin, OOP, Functional Programming, TDD, SOLID]
date: 2018-01-08 07:20:00 PM UTC
---

<!-- January 9, 2018 3:20:00 AM Philippine Time -->


![old-resume-technical-expertise-oo.png](/images/2018/old-resume-technical-expertise-oo.png)

That image is part of my r&eacute;sum&eacute; when I applied for my first and second jobs.

_Object-Oriented Programming was one of my technical expertise!_

I can't help but laugh at myself when, years later, I heard Uncle Bob Martin talk about [programmers claiming to know about OOP when they do not truly know OOP.](https://youtu.be/Nsjsiz2A9mg?t=34m5s)

<!--more-->


> Oh we're doing OO!
<br /><br />
> What's OO?
<br /><br />
> ... this ... and ... that ... 
<br /><br />
> Oh yeah, I've been doing that for years.

:laughing:


Well, I did not not know any better during that time. I thought OOP was just knowing what a class is, knowing what an object is, what an interface is, what inheritance is, what polymorphism is...

But I passed the interviews, of course...

I remember this question during my interview for my second job:

> **Interviewer:** Do you know of the other way of doing polymorphism than using an interface?
<br /><br />
> **Me:** Uhmmmm... Using a child class and a superclass??
<br /><br />
> **Interviewer:** You mean inheritance?
<br /><br />
> **Me:** Yes... inheritance

:laughing:

Well, I think my answer is not completely wrong but... I don't know...

Perhaps my interviewers just forgave my arrogant claim about OOP because they knew that I was just a beginner.

Okay... enough of my story...

I just used my story on OOP as an introduction to this post because it is very much related to what this post is all about.


This post is about Mark Seemann's<sup id="footnote-indicator-1">[[1]](#footnote-1)</sup> talk titled ["Functional Architecture --- The pits of success (NDC Sydney 2016)"](https://www.youtube.com/watch?v=US8QG9I1XW0).

I find this talk very interesting because he has claims in this talk which will give lots of hope to programmers.

> ... This is what I feel to be a software architect or a lead developer on a team is you have to be constantly vigilant because if you just look away for a moment, if you are sick for a couple of days, or you go on a vacation, or you have to go to many meetings, what's going to happen is that everything rolls downhill again...
<br /><br />
> ... Then about 5 or 6 years ago, I started learning about functional programming...
<br /><br />
> I realized that **a lot of these things that are difficult in object-oriented design actually turns out to be quite easy to do with functional programming**. It almost happens by itself.

_Whoa!_

## Clean Architecture and OO

He talked about the difficulty of learning decoupled architectures when used with object-orientation:

> ... You don't want your business logic to be too dependent on all of those technical concerns (such as the UI, the database, and sending emails) because they may change...
So you want to protect the valuable parts of you software from all the incidental details...
<br /><br />
My experience with this though is that it's really difficult just to explain to a team of software developers who have never heard about this before why you would want to do this.
<br /><br />
Because it goes into a lot of things about the principles of object oriented design like the SOLID principles for example; and you need to think about Dependency Injection... In order to understand those things you have to read thick books about them...


I think I can relate to this because it took me about four or five years before realizing the importance of the SOLID principles and many things similar to them. I heard about these things from the beginning of my career, even during college I think, but I did not give that much attention to them. I was so focused on the _shiny_ things in programming --- the frameworks and libraries --- which are popping from everywhere every millisecond of the day. :laughing:

## Better than OO!

> If we need that many pages (500 or 700 pages) to explain a concept maybe we should start to think about if there is a better way. --- Is this really the best we can do?

Oooooooo... There is a better way!

> Does functional programming help? It does!

... Then he talks about how functional programming might be a better way than object-orientation.

This is very intersting!

I first became interested with functional programming [through Uncle Bob Martin](http://blog.cleancoder.com/uncle-bob/2012/08/24/functional-programming-for-the-object-oriented-programmer.html). But my interest about learning it decreased after reading this statement from him also, in his post titled ["Living on the Plateau"](http://blog.cleancoder.com/uncle-bob/2017/11/18/OnThePlateau.html):

> If we aren’t going to see 1024 core processors in the near future, what need have we of functional programming languages? Oh, don’t get me wrong. I think functional programming is a good idea. Every programmer should learn it. But the crisis that we anticipated – the crisis that drove the current infatuation with functional languages –-- seems not to be occurring. And that may well mean that functional languages never achieve the ascendency that we had anticipated for them. It may just be that Java/C#, and Ruby/Python, and Swift/Dart/Go are, and will be, sufficient.



... But after viewing Mark Seemann's talk... _I have to learn functional programming._
<!-- 
The only thing I know today about functional programming is that the use of assignment is discouraged and that it uses lots of recursion. People also talk about this _monad_ thing, which even Scott Hanselman find hard to understand, as he said in a facebook post a few months ago.
 -->


## Better than TDD?!

Mark Seemann also talked about testing and why it is easier in functional programming than in object-orientation:

> Testable OOP requires a lot of effort and a lot of diligence and a lot of constant monitoring of what's going on...

Then this!...

> If I had a team of developers who are already good at doing functional programming, I could basically just say to them, if I were the lead developer or software architect, **"just write as many pure functions as you can"**
<br /><br />
> ... then I'll go on a holiday and **then I'll go back and we will start testing it**.

_Whoaaa! What?!... Go back and start testing?!_

He said that pure functions are **always** [testable](/2017/12/19/tdd-and-teaching-design-without-a-teacher)!

Does that mean that [TDD](/memorabilia/quotes/tdd/) will not be needed in this kind of setting?

Does that mean that [writing tests after-the-fact](/memorabilia/videos/expecting-professionalism-by-uncle-bob-martin/#testing-legacy-code) will not be very difficult in functional programming?

I hope...



----------

<sup id="footnote-1">[[1]](#footnote-indicator-1)</sup> 
<small>Mark Seeman... He was the one who made me understand the SOLID principles of object-oriented design... from his Pluralsight course _"Encapsulation & SOLID"_... that was during the time when I was still [stealing courses from Pluralsight](/2017/03/27/why-I-started-buying-physical-books)... :grin: </small>
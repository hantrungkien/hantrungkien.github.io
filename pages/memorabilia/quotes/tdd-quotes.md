---
layout: page
title: TDD Quotes
categories: [Programming]
tags: [TDD]
permalink: /memorabilia/quotes/tdd/
---

I believe, like [Uncle Bob Martin does](http://blog.cleancoder.com/uncle-bob/2014/05/02/ProfessionalismAndTDD.html), that, _today_, TDD (or Test-Driven Development) is one of the hallmarks of professionalism in the software development world.

So I would like to convince myself and my fellow software developers to embrace TDD. :smile:

Ergo, these quotes...



### Uncle Bob Martin <small>([So... You want your code to be maintainable?](https://sites.google.com/site/unclebobconsultingllc/so-you-want-your-code-to-be-maintainable))</small>

> "**Nothing makes a system more flexible than a suite of tests.** 
<br /><br />
Nothing. 
<br /><br />
Good architecture and design are important; but the effect of a robust suite of tests is **an order of magnitude greater**. It’s so much greater because those tests enable you to improve the design.
<br /><br />
> "This can’t be overstated. If you want your systems to be flexible, write tests. If you want your systems to be reusable, write tests. If you want your systems to be maintainable, write tests.
<br /><br />
"And write your tests using the Three Laws of TDD."


### Michael Feathers <small>([Working Effectively with Legacy Code](https://www.bookdepository.com/Working-Effectively-with-Legacy-Code-Michael-Feathers/9780131177055?a_aid=jflaga))</small>

> "**Code without tests is bad code.** It doesn't matter how well written it is; it doesn't
matter how pretty or object-oriented or well encapsulated it is.
<br /><br />
> "With tests, we can change the behavior of our code quickly and verifiably. Without them, we really don't know if our code is getting better or worse."



### Uncle Bob Martin <small>([TDD Harms Architecture](http://blog.cleancoder.com/uncle-bob/2017/03/03/TDD-Harms-Architecture.html))</small>

> "The idea that the high level design and architecture of a system emerge from TDD is, frankly, absurd. **Before you begin to code any software project, you need to have some architectural vision in place. TDD will not, and can not, provide this vision.** That is not TDD’s role."
<br /><br />
> However, this does not mean that designs do not emerge from TDD –-- they do; just not at the highest levels. **The designs that emerge from TDD are one or two steps above the code**; and they are intimately connected to the code, and to the red-green-refactor cycle.
<br /><br />
> It works like this: ..."



### Micheal Feathers <small>([The Deep Synergy Between Testability and Good Design - NDC 2010](https://www.youtube.com/watch?v=4cVZvoFGJTU))</small>

> "If your code is not testable, then it is not a good design."

> "In general, every time you encounter a testability problem, there is an underlying design problem."

> "There is a big difference between mentally knowing about coupling and feeling the pain of coupling... But **when we actually write tests, we feel concrete pain**. The concrete pain is not because testing is difficult, it's because we need to change our design."

> "I can have all these interesting thoughts about design. But if I write my tests first, it's an instant concrete reminder of whether things are actually aligned pretty well with good design principles or not."

> "If you're finding trouble testing things, reconsider your design and end up with something better."



### Uncle Bob Martin <small>(Expecting Professionalism - Kuppelsalen, Copenhagen - December 15, 2015)</small>


> **TDD minimizes debugging time.**

> TDD is a good way to make code example for the programmer to read.

> TDD makes writing code fun.

> **TDD makes you write decoupled code** (decoupled code == testable code) which can make the design of the system better.


> TDD gives you a suite of tests that you trust with your life. And when you have that suite of tests, you can do many other things like cleaning code and cleaning the design.
<br /><br />
> Nothing makes code more flexible and maintainable than having a suite of tests by a huge order of magnitude.
<br /><br />
> You give me an application that is beautifully designed but there's no tests. I'll be afraid to touch it. It will rot.
<br /><br />
> You give me an application that is badly designed but has a comprehensive suite of tests. I can make the design better because I have a suite of tests.
<br /><br />
> A suite of tests is more important than a good design.



### Joshua Kerievsky <small>(Refactoring to Patterns)</small>

> "Test-driven development and continuous refactoring, two of the many excellent XP practices, have dramatically improved the way I build software. 
<br /><br />
>" I’ve found that these two practices have helped me and the organizations I’ve worked for **spend less time over-engineering and under-engineering and more time creating high-quality, function-rich code, produced on time**."



### Harry Percival (["Test-Driven Development with Python"](https://www.obeythetestinggoat.com/book/praise.harry.html))

> I’ve lost count of the number of times I’ve thought “Thanks, tests”, as a functional test uncovers a regression we would never have predicted, or a unit test saves me from making a really silly logic error. **Psychologically, [TDD] made development a much less stressful process. It produces code that’s a pleasure to work with.** (from [Preface](https://www.obeythetestinggoat.com/book/preface.html))



> Ultimately, programming is hard. Often, we are smart, so we succeed. TDD is there to help us out when we’re not so smart. Kent Beck (who basically invented TDD) uses the metaphor of lifting a bucket of water out of a well with a rope: when the well isn’t too deep, and the bucket isn’t very full, it’s easy. And even lifting a full bucket is pretty easy at first. But after a while, you’re going to get tired. **TDD is like having a ratchet that lets you save your progress, take a break, and make sure you never slip backwards. That way you don’t have to be smart all the time.** (from [Chapter 4](https://www.obeythetestinggoat.com/book/chapter_philosophy_and_refactoring.html))


### Michael ([GeePaw](http://anarchycreek.com/whosgeepawhill/)) Hill ([How TDD and Pairing Increase Production](http://anarchycreek.com/2009/05/26/how-tdd-and-pairing-increase-production/))

> ... the hard part of programming is the thinking, not the typing...
<br /><br />
> TDD increases your production because it serves as a thinking-aid.  It limits back-tracking and gold-plating  and it reduces code-study and debugging.  Pairing increases your production for the very same reason.  Two developers together don’t type as fast as two developers separately, but we don’t care: **the bottleneck is the thinking, and pairing and TDDing both improve it.**




## Other useful TDD quotes


> "**TDD isn’t something that comes naturally. It’s a discipline**, like a martial art, and just like in a Kung Fu movie, you need a bad-tempered and unreasonable master to force you to learn the discipline."
<br /><br />
> --- Harry Percival (from [Chapter 1 of "Test-Driven Development with Python"](https://www.obeythetestinggoat.com/book/chapter_01.html))

> "TDD is a discipline, and that means it’s not something that comes naturally; **because many of the payoffs aren’t immediate but only come in the longer term, you have to force yourself to do it in the moment.**"
<br /><br />
> --- Harry Percival (from [Chapter 4 of "Test-Driven Development with Python"](https://www.obeythetestinggoat.com/book/chapter_philosophy_and_refactoring.html))
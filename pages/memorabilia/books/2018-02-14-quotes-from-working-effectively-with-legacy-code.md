---
layout: page
title: Great Quotes from "Working Effectively with Legacy Code" by Michael Feathers
categories: []
tags: [Michael Feathers]
date: 2018-03-14 01:00:00 PM UTC
permalink: /memorabilia/books/quotes-from-working-effectively-with-legacy-code/
---

Some uplifting criticisms and some encouraging words from ["Working Effectively with Legacy Code" of Michael Feathers](https://www.bookdepository.com/Working-Effectively-with-Legacy-Code-Michael-Feathers/9780131177055?a_aid=jflaga)

(The quotes below are words that might help change the mindset of programmers on dealing with legacy code. They are not about how to _reverse_ the rot in a legacy code, which is what the majority of the book contains. Read the book if you want to know about the techniques. :smile:)


### Preface

> "**Code without tests is bad code.**
<br /><br />
> It doesn't matter how well written it is; it doesn't matter how pretty or object-oriented or well-encapsulated it is. 
<br /><br />
> **With tests, we can change the behavior of our code quickly and verifiably.**
<br /><br />
> Without them, we really don't know if our code is getting better or worse."
<br /><br />
> --- Michael Feathers


----------

### Chapter 6

> When I work with teams, I often start by asking them to take part in an **experiment**. For an iteration, we try to make no change to the code without having tests that cover the change. If anyone thinks that they can't write a test, they have to call a quick meeting in which they ask the group whether it is possible to write the test.
<br /><br />
The beginnings of those iterations are terrible. People feel that they aren't getting all the work done that they need to. But slowly, they start to discover that they are revisiting better code. Their changes are getting easier, and they know in their gut that this is what it takes to move forward in a better way.
<br /><br />
It takes time for a team to get over that hump, **but if there is one thing that I could instantaneously do for every team in the world, it would be to give them that shared experience, that experience that you can see in their faces: "Boy, we aren't going back to that again."**


> The biggest obstacle to improvement in large code bases is the existing code. "Duh." you might say. But I'm not talking about how hard it is to work in difficult code; **I'm talking about what that code leads you to believe.**
<br /><br />
If you spend most of your day wading through ugly code, it's very easy to believe that it will alway be ugly and that any little thing that you do to make it better is simply not worth it. You might think, "What does it matter whether I make this little peice nicer if 90 percent of the time I'll still be working with murky slime? Sure, I can make this piece better, but what will that do for me this afternoon? Tomorrow?"
<br /><br />
Well, if you look at it that way, I'd have to agree with you. No much.
<br /><br />
**But if you consistently do these little improvements, your system will start to look significantly different over the course of a couple of months.** At some point, you'll come to work in the morning expecting to sink your hands into some slime and discover, "Huh, this code looks pretty good. It looks like someone was in here refactoring recently." At that point, when you feel the difference between good code and bad code in your gut, you are a changed person...


### Chapter 7

> **The human mind has some interesting qualities. If we have to perform a short task (5-10 seconds long) and we can only take a step once every minute, we usually do it and then pause.** If we have to do some work to figure out what to do at the next step, **we start to plan**. After we plan, our minds wander until we can do the next step.
<br /><br />
**If we compress the time between steps down from a minute to a few seconds, the quality of the mental work becomes different.** We can use feedback to try out approaches quickly. Our work becomes more like driving than like waiting at a bus stop. Our concentration is more intense because we aren't constantly waiting for the next chance to do something. Most important, the amount of time that it takes us to notice and correct mistakes is much smaller



### Chapter 8

> ... if we have tests in place, we are able to remove duplication easily.



### Chapter 13

> No, finding bugs in legacy code usually isn't a problem. In terms of strategy, it can actually be misdirected effort. **It is usually better to do something that helps your team start to write correct code consistently.** The way to win is to concentrate effort on not putting bugs into code in the first place.
<br /><br />
Automated tests are a very important tool, but not for bug finding --- not directly, at least. In general, automated tests should specify a goal that we'd like to fulfill or attempt to preserve behavior that is already there. In the natural flow of development, **tests that specify become tests that preserve**. You will find bugs, but usually not the first time that a test is run. You find bugs in later runs when you change behavior that you didn't expect to.



### Chapter 17

> **The brutal truth is that architecture is too important to be left exclusively to a few people.** It's fine to have an architect, but the key way to keep an architecture intact is to make sure that everyone on the team knows what it is and has a stake in it.
<br /><br />
**Every person who is touching the code should know the architecture, and everyone else who touches the code should be able to benefit from what that person has learned.** When everyone is working off of the same set of ideas, the overall system intelligence of the team is amplified. If you have, say, a team of 20 and only 3 people know the architecture in detail, either those 3 have to do a lot to keep the other 17 people on track, or the other 17 people just make mistakes caused by unfamiliarity with the big picture.



### Chapter 21

> **One of the startling things that you discover when you start removing duplication zealously is that designs emerge.** You don't have to plan most of the knobs in you application; they just happen.

> Duplication removal is a powerful way of distilling a design. It not only makes a design more flexible, but it also makes change faster and easier.

> When we remove duplication, our code often naturally starts to fall in line with the Open/Closed Principle.



### Chapter 23

> ... The truth is, there are many different kind of "smart." Holding on to a lot of state mentally can be useful, but it doesn't really make us better at desicion making. At this point in my career, I think I'm a much better programmer than I used to be, even though I know less about the details of each language I work in. Judgement is a key programming skill, and we can get into trouble when we try to act like super-smart programmers.



### Chapter 24

> Working in legacy code is difficult. There is no denying it. Although every situation is different, one thing is going to make the job worth it to you as a programmer or not: figuring out what is in it for you.

> The key to thriving in legacy code is finding what motivates you.

> If morale is low on your team, and it's low because of code quality, here's something that you can try: Pick the ugliest most obnoxious set of classes in the project, and get them under test. **When you've tackles the worst problem as a team, you'll feel in control of the situation. I've seen it again and again.**

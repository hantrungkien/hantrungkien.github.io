---
layout: post
title: 'My third physical book on programming: Growing Object-Oriented Software Guided By Tests'
category: Programming
tags: [Book, OOP, TDD, SOLID Principles, Design Patterns, Joel Rodriguez, GOOS (Growing Object-Oriented Software)]
date: 2017-04-30 03:40:00 PM UTC
---

<!-- April 30, 2017 11:50:00 PM Philippine Time -->


Like I said before, [I started to buying physical programming books](/2017/03/27/why-I-started-buying-physical-books/) this year (2017).

About a month ago, I started to look for the next book to buy. I was considering books on TDD, OOP, or Architecture; and something that can help me do unit testing because I'm planning to introduce it to the current project I am working on. 

The book title ["Growing Object Oriented Software Guided by Tests"](https://www.bookdepository.com/book/9780321503626?a_aid=jflaga) sounded very good. So I started googling for reviews for that book.

<!--more-->

[One of the reviews that I found was Steve Smith's.](http://ardalis.com/growing-object-oriented-software-guided-by-tests-book-review) I was a .NET developer si his name is familiar to me _(I think his name is famous in the .NET world)_.

One thing from the review that made me interested about the book is this quote:

> “We value code that is easy to maintain over code that is easy to write.”

Another thing is the part where Steve Smith disagrees with the authors of the book:

> I made one note where I have to disagree with the authors. On page 297 they note their preference “not to name classes or interfaces after patterns” using terms like “Repository.” Their argument is that “the clients of [a class] do not care what patterns it uses.” Here I respectfully disagree, since frequently the use of a pattern name in the name of a class makes its intent and how one expects to use it much more clear.


I was very interested because during the time I was reading Steve Smith's review, I was having a task where, I think, the resulting structure of my code looks like it follows the template and strategy patterns; but the classes that I created do not follow the standard naming of template and strategy patterns. I'm not even sure if there are standard names for the classes and interfaces involved in these patterns. (Maybe they don't have standard names??)

All that was in my mind is that as long as I am able to make the dependencies of the modules  manageable, while following what I understood about OOP principles, everything will be okay.*


... so that made interested to know what the reasoning is behind the advise of not naming classes based on the standard names of the design patterns.

My initial thoughts about the reasoning behind the advise of the authors is that, maybe, they were thinking about the _requirements constantly changing_ problem: when the requirements change, the implementation might change, and our code might change so that the pattern that we previously used is not the same as the pattern we are using in the new implementation. And if we previously named our classes based on the known patterns, and now we change it to use a different pattern, the ones that will be reading our code in the future might get confused. _"Why is this class named like this pattern when it is using another pattern?"_

Well, I'm not sure. I already have [the book](https://www.bookdepository.com/book/9780321503626?a_aid=jflaga). It arrived about a week ago. So I have to finish the book to confirm those thoughts. :smile:

[![Growing Object-Oriented Software Guided By Tests - Book](/images/2017/growing-oo-software-guided-by-tests-book.jpg)](https://www.bookdepository.com/book/9780321503626?a_aid=jflaga)

<br /><br />

<small>
\* I got this idea of not being very much obsessed with design patterns from ["Don’t Get Obsessed With Design Patterns"](https://simpleprogrammer.com/2016/06/15/dont-get-obsessed-design-patterns/) by Joel Rodriguez...
</small>

<blockquote>
    <small>
    I believe that knowing object-oriented design principles and applying best practices like SOLID, KISS and YAGNI are far more important than design patterns themselves. If you apply these principles, patterns will come out naturally.
    </small>
</blockquote>

<small>
... and from ["What Are Software Design Patterns Hiding From You?"](https://simpleprogrammer.com/2016/12/28/software-design-patterns-hiding/) by Muhammad Umair.
</small>

<blockquote>
    <small>
    I ask for you to not try too hard with the documented software design patterns (especially when you are starting). We use patterns all the time in our daily lives, and you should focus on these first.
    </small>
</blockquote>
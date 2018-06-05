---
layout: post
title: '"Working Effectively with Legacy Code" of Michael Feathers'
categories: [Programming, Book]
tags: []
date: 2018-04-30 12:00:00 AM UTC
---

<!-- April 28, 2018 05:33:00 AM Philippine Time -->


> "For a long time it’s puzzled me that most books on software development
processes talk about what to do when you are starting from a blank sheet
of editor screen. It’s puzzled me because that’s not the most common situation
that people write code in. Most people have to make changes to an
existing code base, even if it’s their own. In an ideal world this code base
is well designed and well factored, but we all know how often the ideal
world appears in our career.
<br /><br />
> "So this book is important because it’s written from the perspective of
what to do with an imperfect yet valuable code base."
<br /><br />
> --- Martin Fowler


<!--more-->


That quote above is from the Foreword of the book ["Object-Oriented Reengineering Patterns."](http://scg.unibe.ch/download/oorp/)

But I think the same statement can also be made with the book ["Working Effectively with Legacy Code"]((https://www.bookdepository.com/Working-Effectively-with-Legacy-Code-Michael-Feathers/9780131177055?a_aid=jflaga)) of Michael Feathers (as hinted in [GOOS](/2017/04/30/my-third-physical-programming-book))

In this book, Micheal Feather presents some techniques on how to _reverse_ the rot in legacy code.

What is "legacy code"?

Micheal Feathers offers a very direct yet controversial definition:

> **"Legacy code is code without tests"**

Then this:

> "**Code without tests is bad code.**
<br /><br />
> It doesn't matter how well written it is; it doesn't matter how pretty or object-oriented or well-encapsulated it is. 
<br /><br />
> **With tests, we can change the behavior of our code quickly and verifiably.**
<br /><br />
> Without them, we really don't know if our code is getting better or worse."

_Wow!_ It seems like Micheal Feathers value tests so highly [as Uncle Bob does](https://sites.google.com/site/unclebobconsultingllc/so-you-want-your-code-to-be-maintainable)!

... _We need to start writing tests for our code then!_ :grin:

But if you will not be convinced that writing tests are very important, this book will still help in changing your mindset about rotting legacy code --- this book can give you hope that the rot is _reversible_.

I compiled some very interesting ideas I got from the book: [Great Quotes from "Working Effectively with Legacy Code" by Michael Feathers.](/memorabilia/books/quotes-from-working-effectively-with-legacy-code/)

I also found (through [here](https://softwareengineering.stackexchange.com/questions/122014/what-are-the-key-points-of-working-effectively-with-legacy-code)) a [short PDF on the _key points_](http://www.netobjectives.com/system/files/WorkingEffectivelyWithLegacyCode.pdf) of the book. You might want to read it before reading the book.

----------

In case you are still in doubt on whether it is worth spending time reading this book...

Many of our other masters highly recommend this book.

Uncle Bob Martin wrote the Foreword for the book:

> "... It's not enough to prevent the rot --- you have to be able to reverse it. That's what this book is about"

[Woody Zuill, one of my heroes,](/2017/10/14/mob-programming-of-woody-zuill) recommends it in his ["Agile Books I Recommend"](http://zuill.us/WoodyZuill/agile-books-i-recommend/).


John Sonmez of simpleprogrammer.com recommends it [here](https://simpleprogrammer.com/maintaining-code/) and [here](https://simpleprogrammer.com/best-books-software-developers/)

> Every software developer should read this book, since every software developer is likely to spend a majority of their time working with legacy code.


And someone who is [giving away books for free?](http://blog.jayfields.com/2015/06/drop-books.html)... Jay Fields

> "These books, all technical, are books that I think most programmers will benefit from reading."


Scott Hanselman had an interview with Micheal Feathers [here.](https://www.hanselminutes.com/165/working-effectively-with-legacy-code-with-michael-feathers)

_Happy reading!!!_

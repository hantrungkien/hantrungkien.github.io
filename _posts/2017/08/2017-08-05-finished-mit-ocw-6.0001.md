---
layout: post
title: I finished MIT OpenCourseWare 6.0001! Yehey!
categories: [Programming]
tags: [MIT OCW 6.0001, Python, Robert Martin, TDD]
date: 2017-08-05 04:35:00 PM UTC
---

<!-- August 06, 2017 12:35:00 PM Philippine Time -->

[MIT OCW 6.0001](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-0001-introduction-to-computer-science-and-programming-in-python-fall-2016/index.htm) helps people understand the basics of data structures and algorithms, recursion, and Object-Oriented Programming.

<!--more-->

I already have a considerably good(?) amount of knowledge about the basics of these topics (through Stanford's free course named CS-106B, and from some books that I have read, and of course from my experiences as a software developer for more than 4 years already), but I consumed 6.0001,

- first, to become more familiar with Python (there are free and good materials available online which uses Python: for instance, [greenteapress.com](http://greenteapress.com/wp/)),
- and, second, to prepare myself for [6.0002](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-0002-introduction-to-computational-thinking-and-data-science-fall-2016/index.htm), which teaches the basics of data science.

Data science does not really like me (at least for now). :laughing: But I have observed that these field of studies have this property where, even though they do not like you at first, they will eventually like you if you push yourself to like them first. :laughing:

Maybe not?? But I'm hoping that data science will eventually like me and will give some space in its territory for me to occupy.
<!-- importunate -->

Yehey again!...

My answers to the assignments of 6.0001 is in this GitHub repository: [github.com/jeremiahflaga/mit-ocw-6.0001](https://github.com/jeremiahflaga/mit-ocw-6.0001).

(I was actually introduced to an older version of this course last 2010 --- MIT OCW 6.00 2008 version --- but my mistake was that I did not do the asignments... I only watched the lectures... I wanted to finish things as fast as I could during those days! :grin:)

## Dynamically Typed Languages and TDD

Also, one thing I noticed when using Python (while doing the assignments) is that it seems like TDD is very needed when using dynamically typed languages, most especially with programmers who are not used to commenting their codes (like me --- because I learned from the book "Clean Code" that expressive code is more desirable than comments or documentation, because comments and docs could lie, but the code never lies... and, I'm not saying that I _always_ write expressive code --- only that I _aspire_ to write expressive code).

But in Python (and maybe in other dynamically typed languages like Ruby), it seems like it is encouraged to document the classes and methods that are being written. And I can understand why --- you have to tell the users of your classes/methods what _types_ of objects they should pass as parameters.

I experienced this when doing Problem Set 4 of 6.0001. The introduction of the specification says that there will be deductions for voilations such as _"uncommented code"_.

What??

Okay. But when I started coding, I noticed that the code templates for Problem Set 4 already have comments in them. That lessens the burden for me. :smile:

Actually, nobody is checking my code, so it did not matter whether I write comments or not. :laughing: (But I wanted to follow the instructions in the problem sets of course. I instead created unit tests for Problem sets 4b and 4c.)

<!--
So I did not have to write comments... Great! (But because I wanted to become familiar with how to do unit testing in Python, I created `ps4b_test.py` and `ps4c_test.py` for the second and third part of Problem Set 4.)
-->

So yes...

If we do not want to write comments/docs for our classes/methods when using a dynamically typed language, such as Python, I think we have to do TDD. The tests that we write while doing TDD will now serve as the documentation for our classes/methods (like what Uncle Bob Martin says in his talks). If the users of our classes/methods are confused about how to use them, they can just look at the tests and see clearly how to use them.

So... TDD can help us write documentations that never lie.

I'm wondering... when will TDD become the mainstream method for documentation?

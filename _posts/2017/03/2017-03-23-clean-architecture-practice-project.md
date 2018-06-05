---
layout: post
title: Clean Architecture Practice Project
category: Programming
tags: [Programming, Clean Code, Clean Architecture, TDD, Robert Martin, Matthew Renze]
date: 2017-03-23 01:00:00 AM UTC
---

<!-- March 23, 2017 9:00:00 AM Philippine Time -->

<small>(Originally written on March 21, 2017)</small>

<small>(The contents of this post might be outdated. The [README in this project's GitHub repository](https://github.com/jeremiahflaga/clean-architecture-practice/blob/master/README.md) might have updates.)</small>

Last year, after learning that Robert C. Martin of the "Clean Code" book has a blog (through a [link](http://blog.cleancoder.com/uncle-bob/2015/11/18/TheProgrammersOath.html) shared in our Skype group by a coleague, I&ntilde;aki Narciso, who later became a friend), I started reading anything in that blog whose title catches my attention. _(I was not very aware that busy people, like Robert C. Martin, have blogs.)_

I was able to read his article ["The Clean Architecture"](http://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html). While reading that article I thought that he is just explaining how _most_ software developers do architecture in the real world. And that all I have to do to be able to experience this clean architecture thing is to wait until I can find a job where the project I will be involved in uses this kind of architecture.

<!--more-->

But two days ago, I learned that he is writing a new book titled "Clean Architecture" to be released this August 2017 (according to Amazon). _(I'm going to buy that book.)_

I realized that this **"Clean Architecture"** idea is new. I have to learn it. _(Maybe it's not really new; but maybe the majority of developers does not know about it yet?!)_

While looking for examples of _Clean Architecture_ I stumbled upon Matthew Renze's [website](http://www.matthewrenze.com/presentations.html#clean-architecture). (I remember that I saw this sample project about a year ago but I did not give it that much attention. Maybe because I did not yet understand some parts of the app?! Maybe. :disappointed:)

I tried to study Matthew Renze's [sample project](https://github.com/matthewrenze/clean-architecture-demo) through his [slides](http://www.matthewrenze.com/presentations/clean-architecture.pdf). (He has a Pluralsight course on this. I will save some money to be able to access them later if things are not yet clear after reading Uncle Bob's book.)

I also found the article ["a Clean Architecture in .Net"](https://medium.com/@stephanhoekstra/clean-architecture-in-net-8eed6c224c50#.wwhi7no7o) by Stephan Hoekstra.

Great!!!

## I'm going to practice doing clean architecture! In this practice project...

1. I'm going to try to redo Stephan Hoekstra's ["Contact Real Estate Agent" project](https://github.com/stephanhoekstra/clean-architecture).

2. Because I want to know what TDD is, I will try to write my tests first.

3. Matthew Renze has a module named Specification in his project. I think he is trying to separate the tests for the specification from the unit tests. That is what I'm going to do in my practice project.
<br /><br />
Ahh! In his [Git commits](https://github.com/matthewrenze/clean-architecture-demo/commits/master), he has this: "Added Specification project for acceptance tests". So the Specification module contains the acceptance tests.

4. In Stephan Hoekstra's project, he has this `Interest` entity. But his `House` entity has this:
<br />
``` csharp
public IList<Interest> Leads { get;  }
```
<br />
What is this `Leads`?
<br /><br />
Ahh! So the `Interest` class is a [_"sales lead"_](http://www.investopedia.com/terms/s/sales-lead.asp). I'm going to use `SalesLead` instead of `Interest`. I'm not sure if this is correct, but I will use `SalesLead` because it seems more clear to me than `Interest`. I will just change it later if I find out that I'm wrong.

Happy coding!!! :smile:
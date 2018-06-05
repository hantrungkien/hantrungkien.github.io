---
layout: page
title: '"Expecting Professionalism" by Uncle Bob Martin'
category: Programming
tags: [Programming, Robert Martin, TDD, Professionalism]
date: 2017-05-05 10:45:00 PM UTC
permalink: /memorabilia/videos/expecting-professionalism-by-uncle-bob-martin/
---

<!-- May 06, 2017 06:45:00 AM Philippine Time -->


Expecting Professionalism by Uncle Bob Martin - Kuppelsalen, Copenhagen - Organized by Danske Bank, Denmark - December 15, 2015

<div style="position:relative;height:0;padding-bottom:56.25%"><iframe src="https://www.youtube.com/embed/BSaAMQVq01E?ecver=2" width="640" height="360" frameborder="0" style="position:absolute;width:100%;height:100%;left:0" allowfullscreen></iframe></div>



<div id="summary" class="message message-compressed float-left">
	<strong>Summary of Uncle Bob's Expectations</strong>
	<ol>
		<li>
		We should not ship shit.
		</li>
		<li>
		We will always be ready
		</li>
		<li>
		Stable Productivity
		</li>
		<li>
		Inexpensive adaptability
		</li>
		<li>
		Continuous improvement
		</li>
		<li>
		Fearless competence
		</li>
		<li>
		Extreme quality
		</li>
		<li>
		We will not dump on QA
		</li>
		<li>
		QA will find nothing
		</li>
		<li>
		Automation
		</li>
		<li>
		Nothing fragile
		</li>
		<li>
		We cover for each other
		</li>
		<li>
		Honest estimates
		</li>
		<li>
		I expect you to say "No"
		</li>
		<li>
		Continuous aggressive learning
		</li>
		<li>
		Mentoring
		</li>
	</ol>

	<i>please see below for more explaination...</i>
</div>


<small>(9:20)</small>

Boolean algebra basics	


<small>(10:40)</small>

Many of us wanted to be programmers because we felt the power of making the machine do our bidding.



<h2 id="problem-no-profession">
	We do not have a profession
</h2>

<small>(11:15)</small>

We have a problem: **we do not have a profession.**

We have a job/task. But we don't have ethics. We have never defined ethics to our job. We have never defined a set of practices or disciplines.

We cannot say that we have a profession because there is nothing that we profess.

**And this is a problem because we _rule_ the world**. We didn't know this; we didn't want this; but this has become true. We programmers, you and I, rule the world. Other people think they rule the world. They write the rules down and they give them to us; and we code the rules into the machines that make or civilization work.


<small>(13:45 (some joke, or is it?))</small>

How much code is in a car? A hundred million lines of code in a modern car.

A hundred million lines of code in a modern car.. And you guys.. that should scare the heck out of you.. because you know..

How many people died in cars because of software failures? Many.


We have to come to grips with the fact that **we are killing people.** We didn't get into this business to kill people. We got into this business to print our name infinitely on the screen. But we are killing people. And society does not quite recognize this yet.



<small>(18:50)</small>

We have graduated to the status of _scapegoat_. CEOs can now tell the world "it's our fault"


(We should be offended that those software developers dishonored us in that way. - please watch the video for context)


(What if 10,000 people died because of some software failure?)



<h2 id="standards-and-disciplines">
	Standards and Disciplines
</h2>

<small>(21:30)</small>

.. to avoid it we have to do something other professions have done in the past -- they managed to have **a set of standards and disciplines** before the government does.

If we get there before the government does then when the disaster occurs, and the disaster will occur, and the politicians will rise up in righteous indignation, and will point their fingers at us because 10,000 people died; but if we can say that this is not due to our negligence because here are our disciplines, here are our standards that we follow, here's how we force those standards... this is an accident but it is not our industry that is at fault. And if we can do that we might bypass the worst that the politicians might do to us.


<small>(22:45)</small>

What would these standards be like? What kind of ethical principles should we follow?




<h2 id="expectations">
	Let's assume for a moment that I am your new CTO. I'm going to tell you my expectations.
</h2>

**While hearing these expectations, your brain will react in two ways at the same time.**

> The normal part of your brain will say **"that's a pretty good expectation".**

> The programmer part will react by thinking that **I'm completely insane.**




### My expectations are:

**1. We should not ship shit.**

> We will not knowingly ship code that is defective, substandard


<small>(25:45)</small>

**2. We will always be ready.**

> At the end of each iteration the team should be confident that the code is deployable (meaning of done)


<small>(28:50)</small>

**3. Stable Productivity.**

> We will produce features a year from now just as fast as we produce them today. We will not be slowed down by the mess that we make because we are not going to make the mess.


<small>(32:20)</small>

**4. Inexpensive Adaptability.**

> The software will be easy to change. Business should not find it expensive to adapt the software to new requirements. The code should be easy to change.

> We call it software because it was designed to be easy to change. We invented software so that we can change the behavior of machines easily.

<small>(33:40)</small>

**5. Continuous Improvement.**

> The software gets better with time. The code gets cleaner with time. The design gets better with time.

> The boy scout rule.

<small>(35:10)</small>

**6. Fearless Competence.**

> (Uncle Bob talks about the button that checks whether or code works or not)

> Where can we buy that button?

> TDD - a discipline, the goal of which is to give you that button

> What is the right level of test coverage?
> 
> 100% - the only reasonable answer but also unachievable. But we are used to asymptotic goals; goals that you always approach but never quite get; But you never stop trying.

<small>(41:35)</small>

**7. Extreme Quality.**

> The software is going to work consistently release after release
	
**8. We will not dump on QA**

**9. QA will find nothing**

> "If the software doesn't have to work, I can meet any deadline you set for me."

**10. Automation**

> I expect the vast majority of the testing to be automated.

> The inevitable outcome of manual tests: Manual testing always ends up with you losing the tests. You can lose them directly (like the guy in the example) or you can lose them when the QA decided not to run them because they don't have time.

> There are some tests that you can't automate. And there are some testing that cannot be automated - those that require creative energy - ex. Finding a way to break the system, writing specifications & tests of the system that must pass.

**11. Nothing fragile**

> I expect nothing in the system to be fragile. We should fix the buggy module.

**12. We cover for each other**

> It is your responsibility that someone can cover for you if you go down (got sick for example).

> Examples on how to do this: 
1. pair programming
2. heavy reviews

**13. Honest estimates**

> The most honest estimate: "I don't know"

> Two components of estimate:
1. accuracy and 
2. precision.

> "I don't know is precise but not accurate

> Giving three estimates -- the best, average, and worst cases -- is both precise and accurate.

> Never say "I'll try". The correct answer is "how dare you imply that I am not trying?"

> Saying "I'll try" is tempting to us because we got into this business because we do not like working with people. We don't want to be in a confrontation with people so we want to get rid of them as fast as possible. :)

**14. I expect you to You to say "No"**

> You were hired for your knowledge. You have the position and the responsibility to say _"No"_ when _"No"_ is the right answer.

<small>(1:02:30)</small>

**15. Continuous aggressive learning**

> It is your responsibility, not your employer's, to take care of your career.

**16. Mentoring**

> Half of the programmers in the world have less than 5 years of experience. We are in a state of perpetual inexperience.


		
---

<h1 id="question-and-answer">
	Question and Answer
</h1>


<h2 id="testing-legacy-code">
	About testing legacy code
</h2>


**Question:**

When is the test suite good enough?

**Answer:**

In a legacy environment there is a very large batch of the code that works and it does not need any further testing because it has been through the field, it's been through production, it's a decade old...

So in a legacy environment, the code coverage number is not very significant.

Now how do you deal with a legacy environment?

- **Don't make a project out of making your legacy environment testable (or something like that) because that project will fail.** That's what will happen if you try to make a project to correct a long term lack of discipline.

- **The solution is to change attitude: the boy scout rule.**
	- From now on whenever I or anyone in my team touches this code, we are going to make it a little bit better.
	- If you can make tests do it. If you can't, just do a small change to make it approach testability -- break some coupling, change some function arguments.
	
- Secondly, sometimes you will be asked to add some new features and you'll realize very quickly that there are two ways to add a new feature
	- One way is to smear a bunch of code in the existing legacy code.
	- The other/(second) way is to write the new feature in a completely separate module and then couple that module in from the outside of the legacy code.
	- That second way is the harder of the two and should be the one that you do (because you can write tests).



<h2 id="dont-test-business-rules-through-gui">
	Don't test your business rules through the GUI
</h2>

**Question:**

**Answer:**

<small>(1:21:35)</small>

(Part of the answer to question #2)
**Please don't test your business rules through the GUI.**
Test your business rules through an API that gives you access; the same API that the UI uses.
Design your system so that they are decoupled enough so that you can test your business rules through an API.
Test your systems independent of your UI, databases, etc.




<h2 id="is-tdd-the-answer-to-everything">
	Is TDD the answer to everything?
</h2>


**Question:**

If TDD is the answer to everything then why aren't students learning it at school?

**Answer:**

TDD is not the answer to everything. But it is a very good discipline.

Software is one of those industries that is ahead of academia. Academia is 20 years behind the industry. 

And that is not uncommon. Example is aeronautics. Avaition was first developed.

(About Industry practitioners becoming university professor...) We're still way too young an industry for that to have happened.



<h2 id="thoughts-on-dotnet">
	Thoughts on .NET
</h2>

**Question:**

Question about Uncle Bob's thoughts on .NET and C#

**Answer:**

A fine platform/framework.

One of the problems in going into the Microsoft world is that there is no competition. So you're stuck in a world that is not advancing fast enough.

**I think what we will see in a decade or so is that platforms will survive, the JVM and the CLR will survive. But the languages will shift.**



<h2 id="continuous-delivery">
	Continuous Delivery
</h2>

**Question:**

About continuous delivery.

**Answer:**

If you can do continuous delivery you should do continuous delivery.

(He is currently involved in a project where they trust the test suite so much that they are confident to deploy if all the tests pass)




<h2 id="static-vs-dynamic-typing">
	Static typing vs. dynamic typing
</h2>

<small>(1:32:40)</small>

**Question:**

**Answer:**

(War in the 90s between IBM and Sun regarding static typing and dynamic typing.) <small>[_I found this on Uncle Bob's blog: [Type Wars](http://blog.cleancoder.com/uncle-bob/2016/05/01/TypeWars.html)_]</small>

(Study: People who use dynamically typed languages can develop their systems five times faster than those who use statically typed languages.)

**People agreed that writing in statically typed languages is slow... But it's safer.**

And that was the argument: we prefer safety to speed. Remember this the next time you are worried about a deadline and somebody is hammering you over a deadline: _"the entire industry decided to a go at least twice as slow for the purpose of safety"._


<h2 id="advantages-of-tdd">
	Advantages of TDD
</h2>

<small>(1:35:55)</small>

**How many of you are doing test driven development?**

TDD minimizes debugging time.

TDD is a good way to make code example for the programmer to read.

TDD makes writing code fun.

TDD makes you write decoupled code (decoupled code == testable code) which can make the design of the system better.

TDD gives you a suite of tests that you trust with your life. And when you have that suite of tests, you can do many other things like cleaning code and cleaning the design.



<div class="message message-compressed float-right">
<strong>This is from Uncle Bob's article <a href="https://sites.google.com/site/unclebobconsultingllc/so-you-want-your-code-to-be-maintainable">"So... You want your code to be maintainable."</a></strong>

<p><i>
"So how do we get good design? Well, that’s tricky. Oh it’s not too tricky to get a good design in place at first. <strong>The tricky part is to keep the design good.</strong> That’s the problem, you see. It’s not that the design starts out so bad (although sometimes...) rather it is that the design degrades over time as the system changes."
</i></p>
</div>



Nothing makes code more flexible and maintainable than having a suite of tests by a huge order of magnitude.

> You give me an application that is beautifully designed but there's no tests. I'll be afraid to touch it. It will rot.

> You give me an application that is badly designed but has a comprehensive suite of tests. I can make the design better because I have a suite of tests.

> **A suite of tests is more important than a good design.**



<h2 id="keep-yourself-safe-from-frameworks">
	Keep yourself safe from frameworks
</h2>

**Question:**

About test induced damage of DHH

**Answer:**

A good software developer will look at frameworks with jaded eyes.

Keep yourself safe from frameworks.

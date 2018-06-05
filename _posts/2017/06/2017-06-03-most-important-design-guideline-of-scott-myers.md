---
layout: post
title: Another "one" principle -- The Most Important Design Guideline of Scott Meyers
category: Programming
tags: [Software Design, TDD, Scott Meyers, Jonathan Boccara, Steve McConnell, Robert Martin, Scott Hanselman, Michael Feathers]
date: 2017-06-03 05:00:00 PM UTC
---

<!-- June 4, 2017 01:00:00 AM Philippine Time -->


We programmers tend to be lazy. We don't want to know or remember all those many design principles or guidelines our masters are trying to teach us.


- SOLID.
- Favor composition over inheritance.
- Separate those things that change from those that don't.
- All those design patterns (I only know a few :smile: I'm so lazy!).
- etc.

<!--more-->

Jonathan Boccara said the the [principle that rules them all](https://simpleprogrammer.com/2017/01/27/respecting-abstraction/) is 


> "respecting levels of abstraction";
	

... which he said he first learned from [Code Complete](https://www.bookdepository.com/Code-Complete-Steve-McConnell/9780735619678?a_aid=jflaga) of Steve McConnell;

... which is related to what the authors of the [GOOS book](https://www.bookdepository.com/book/9780321503626?a_aid=jflaga) said on page 252: 

> "All code should emphasize **'what'** it does over **'how'**, including test code."

That is very easy to remember! _Right?_

## Another _"one"_ principle

I think I found another _"one"_ principle or guideline that is easy to remember, and that any programmer can make sense of even if no one is going to explain it to him/her. 

It is Scott Myers' _"Most Important Design Guideline":_

> **Make interfaces easy to use correctly and hard to use incorrectly.**


<span class="message">
_Now, we can stop here and use our imaginations to come up with ideas on how to use that guideline in our code... But if we want to have some initial ideas on how to apply that guideline, then read on... :smile:_
</span>

Scott Myers is the author of [Effective Modern C++](https://www.bookdepository.com/Effective-Modern-C---Scott-Meyers/9781491903995?a_aid=jflaga). I don't really have that book. It only sounds familiar to me because it is one of [_John Sonmez's ultimate list of programming books_](https://simpleprogrammer.com/2015/03/23/the-ultimate-list-of-programming-books/). Go and get it if you are interested.

And now...

<center>:drum_roll: :drum_roll: <small><i>(there's no drum roll!!!)</i></small></center>

<br />

...here is the video of Scott Myers talking about his most important guideline:


<div style="position:relative;height:0;padding-bottom:56.25%"><iframe src="https://www.youtube.com/embed/5tg1ONG18H8?ecver=2" width="640" height="360" frameborder="0" style="position:absolute;width:100%;height:100%;left:0" allowfullscreen></iframe></div>


<br />

<center>:wavy_dash::wavy_dash:</center>

<span class="message message-compressed float-right">
_Note that **TDD**, the discipline that Uncle Bob is promoting in his talks and in his blog, is also in here. Hmmm..._
</span>

And here is the summary of the suggested ways on how to get the results that that guideline is trying to achieve. 


1.  **Adhere to the principle of least astonishment**

	a. Avoid gratuitous incompatibilities with the surrounding environment

	b. Choose good names
	
	c. Be consistent
	
2. **Document interfaces before implementing them**

	- (46:20) proven way to discover interface problems: "If it is unpleasant to explain something, it is probably unpleasant to use it"

	- (47:00) Consistent with Test Driven Design (TDD) - which is involved with having the calling interface established before you actually write the implementation
	
3. **Employ progressive disclosure (to prevent overwhelming the users of the interface with too many choices)**

4. **Introduce types to prevent common errors**

	a. Consider explicitly defining all possible values for the type
	
	b. Avoid over-reliance on string
	

<center>:wavy_dash::wavy_dash:</center>


Scott Myers had also written about the guideline [here](http://www.aristeia.com/Papers/IEEE_Software_JulAug_2004_revised.htm).


Enjoy consuming those resources about that guideline! :yum:



## More...

I think this guideline of Scott Myers is also related to [_"programming by wishful thinking"!_](/2017/05/03/programming-by-wishful-thinking)

Well, who cares right? Everyone reading the masters knows that all these principles/guidelines are related to each other:

<center>:wavy_dash::wavy_dash:</center>

> ["The Single Responsibility and Open/Closed Principle are the Same"](http://michaelfeathers.typepad.com/michael_feathers_blog/2013/07/the-single-responsibility-principle-leads-to-good-openclosed-characteristics.html)
<br />
-- Michael Feathers

<center>:wavy_dash::wavy_dash:</center>

> Scott Hanselman: "Well, ... you're looking at using all of the principles in tandem, **together**"
<br /><br />
> Uncle Bob: "Yes. Well, if you're following the SOLID principles what you're really doing is managing dependencies. All of those principles is about **managing the dependencies between modules**."
<br /><br />
> -- from [Hanselminutes 150 - Uncle Bob Martin: SOLID, this time with feeling](https://hanselminutes.com/150/uncle-bob-martin-solid-this-time-with-feeling) -- starting at about 32:30 in the podcast

<center>:wavy_dash::wavy_dash:</center>

	
<!--
Let's just hope that we, the next generation of programmers, will not keep on reinventing the wheels, most especially the wheels of errors, because we refused to follow those guidelines that were handed to us by our masters.
-->
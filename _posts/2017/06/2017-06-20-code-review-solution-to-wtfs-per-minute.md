---
layout: post
title: 'Code review: the solution to the problem of "WTFs/minute"'
category: Programming
tags: [Code Review, Robert Martin, WTFs/minute, The Crafstman series, Pair Programming, Mob Programming]
date: 2017-06-20 03:30:00 PM UTC
---

<!-- June 20, 2017 11:30:00 AM Philippine Time -->

I recently wrote about [me being a hypocritical Christian](/2017/06/05/am_I_a_hypocrite/) because I sometimes cuss (only in my mind, most of the times, of course; but my attitude has greatly improved since writing that blog post :smile:). 

Christians are not supposed to cuss, right? That's what I was taught. Christians are supposed to possess the _virtue of self-control_. And, I think, cussing is a manifestation of a lack of self-control -- lack of love at the very root, of course, because "love is patient and kind, bears all things, endures all things...".

## ... in programming

In the programming world, there is this joke that says, [_"The only valid measurement of code quality is WTFs/minute"_](http://www.osnews.com/story/19266/WTFs_m).

<!--more-->

Now, let's imagine a world where programmers do not take that as a joke. A world where programmers do not believe that _self-control_ is a virtue ---  where programmers believe in their hearts that "WTFs per minute" is the only valid measurement of code quality. --- How would we manage to prevent the catastrophy that that belief, and the resulting action, would make?

CODE REVIEW of course!!!

If our code base went through peer reviews, then the owner of the whole code base is not each of the individuals in the team, but the whole team itself.

When someone will be heard saying WTF (or any sign of displeasure) while reading code, each individual in the team will think of that as either an attack on the whole team (which includes the attacker of course :laughing:), or as an indicator of displeasure on his own code.

No one in the team will think that the one saying WTF is critisizing someone else.

Instead, everyone will assume that the displeased programmer's mind has these thoughts:

> "What was in our minds when we did this!! :laughing:"

> "Why did I do this crap!"

## Catastrophy prevented!!! Yehey!

I remember this conversation from the [third of The Crafstman series](https://drive.google.com/file/d/0BwhCYaYDn8EgMjc5ZGVjYTQtZmE4NS00MjM0LWIwMDMtMTE2M2NkNTUxNzgx/view) of Uncle Bob Martin:

> I asked: “Jerry, do you do this with your own code too?”
<br /><br />
> Jerry scowled: “We work as a team around here, so there is no code I call my own. Do you consider this code yours now?”
<br /><br />
> “Not anymore.” I said, meekly. “You’ve had a big influence on it.”
<br /><br />
> “We both have.” he said, “And that’s the way that Mr. C likes it. **He doesn’t want any single person owning code**...

<br />
### PS:

Of course _pair programming_ and _mob programming_ can also prevent the catastrophy. :blush:
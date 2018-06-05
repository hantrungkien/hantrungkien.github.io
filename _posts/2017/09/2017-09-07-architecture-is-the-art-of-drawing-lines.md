---
layout: post
title:  Architecture is the art of drawing lines -- Uncle Bob Martin
categories: [Programming]
tags: [Clean Architecture, Robert Martin]
date: 2017-09-07 01:15:00 AM UTC
---

<!-- September 7, 2017 09:15:00 AM Philippine Time -->

> "Architecture is the art of drawing lines"
<br /><br />
> --- Robert Martin

I heard that from Uncle Bob's _"Architecture: The Lost Years (Ruby Midwest 2011)"_ talk.

This is the diagram that he uses in his talk:

![CleanArchitectureDesignByUncleBobMartin.png](/images/2017/CleanArchitectureDesignByUncleBobMartin.png)

Lots of **lines**!

Do you see those two **black lines** in there?

<!--more-->

I will redraw it to emphasize the two **black lines**:

![CleanArchitectureDesignByUncleBobMartin-BlackLinesEmphasized.gif](/images/2017/CleanArchitectureDesignByUncleBobMartin-BlackLinesEmphasized.gif)

Those are the boundaries.

And all **arrowed lines that cross those boundaries** always points inwards --- towards the **most important part/s** of the system.

The reason why they are pointing inwards is so that the _most important part_ will not become slaves of the _details_, as what Uncle Bob calls them, --- so that the _most important part_ will not be affected by the changes that will be made outside its boundaries.

We can redraw the diagram that Uncle Bob uses in that talk to look like this:

![CleanArchitectureDiagramRedrawn.gif](/images/2017/CleanArchitectureDiagramRedrawn.gif)

We can see that **all** the **arrowed lines that cross the boundaries** still points inwards --- towards the middle --- towards what they call the _Business Logic_ part of the diagram.

If we **move** the **black line at the right** side so that it will look like this...

![CleanArchitectureDiagramRedrawnToLookLikeThreeLayersArchitecture.gif](/images/2017/CleanArchitectureDiagramRedrawnToLookLikeThreeLayersArchitecture.gif)

Does that look like the traditional _3-Layers Architecture_ that we know about? --- Where the _Business Logic Layer_, the one at the middle, is **dependent** on the _Data Layer_, the one at the right.

Look at the **arrowed lines that cross the boundaries**...

We can go from 3-Layers Architecture to Clean Architecture, and vice-versa, just by moving the **lines**!?

_Amazing right!_

Of course, moving lines in real world projects is much harder than moving lines in diagrams :laughing: :laughing: :laughing:

But they are doable! Right?


### Update - September 9, 2017

While reading Clean Architecture from Safari Books Online, I found this:

> "... I’ve done this in order to show that architectural boundaries exist everywhere. We, as architects, must be careful to recognize when they are needed. We also have to be aware that such boundaries, fully implemented, are expensive. On the other hand, we also have to recognize that when such boundaries are ignored, they are very expensive to add in later — even in the presence of comprehensive test-suites and refactoring discipline."
<br /><br />
--- Uncle Bob Martin

So... moving the lines might be doable. But it will be hard.


<!--
They should be, or else, we're doomed! :laughing: :laughing: :laughing:
-->

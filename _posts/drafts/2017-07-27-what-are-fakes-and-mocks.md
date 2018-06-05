---
layout: post
title: What are Fakes? and What are Mcoks?
categories: [Programming, Let's ask our masters]
tags: [Fake, Mock, Michael Feathers]
date: 2017-07-27 01:45:00 PM UTC
published: false
---

<!-- August 04, 2017 12:30:00 AM Philippine Time -->

(I have to write something for this week. So here it is...)

A month ago, I had read the first three chapters of ["Working Effectively with Legacy Code"](https://www.bookdepository.com/Working-Effectively-with-Legacy-Code-Michael-Feathers/9780131177055?a_aid=jflaga) of Michael Feathers. It enlightened me about the difference between **fakes** and **mocks**. I'm not sure if I had also read about this in the past. Maybe I had. I can't remember anymore... But this one will make me remember, I'm sure... I hope. (And writing about it will make me remember more surely :laughing:)

(Ahh! I remember that Martin Fowler had written something about this in his website --- "Fakes are not Mocks", or something like that. Google for it if you are interested, but please read on first.)

## So, what are **fakes** and **mocks**?

> "A **fake object** is an object that impersonates some collaborator of your class when it is being tested."
<br /><br />
> --- Michael Feathers

> "Fakes are easy to write... If you have to write a lot of them, you might want to consider a more advanced type of fake called a **mock object**. Mock objects are **fakes that perform assertions internally**."
<br /><br />
> --- Michael Feathers

<!--more-->

So _**fakes**_ are the most primitive type of these _**atik-atik**_ objects... (I mean, the most primitive of these _fake_ objects. But let's call them _atik-atik_ objects here so that I have no need to say _"no pun intended"_ or _"pun intended"_, like what I see others say in their writings. :smile: --- Because many people do not know what _"pun"_ is! _"Pun"_ can mean _"bread"_, right?)

... And _**mocks**_ are more advanced _fakes_.

## Examples?

Okay...

In software development, **decoupled** code is _usually_ considered good code. 

<small>(I would like to say "_always_ considered good", but I can't say that because I only have little expereince in software development. Also, they say that using the word _"always"_ is a sure way to create enemies. So I will avoid using that word to prevent the creation of enemies.)<small>

So when we write software, we usually decouple (or separate) the code that are related to the business we are developing software for (what they call _bussiness logic_) from the code that saves data to the database, for example.

We call those classes that saves data as "repositories"



<!--

**Let's make a little story to make things exciting here...**

## Story...

Year 3030.

Aliens have invaded earth! 

(I don't really believe in aliens, unless I see one... but if angels are aliens too then I believe in aliens :grin:)

_"Earth creatures... we have come come in peace. But if you have no gift to give for us, THERE WILL BE WAAARRRRR!"

Humans gave them gold. They throw them away.

Then a little human gave them a cat.

_"These tiny little creatures are so cuuute!!!"_

They loved cats. They wanted their cats to be forever remembered.

So they commissioned humans to write software that will store information for each alien and the cats that they owned .

_"It must be good!"_ they demanded.

**Decoupled** is what **good** means on earth.

So humans started to creat _models_ in their code...

``` csharp
class Alien {
    public string Name {get; set;}
}

class Cat {
    public string Name {get; set;}
}

-->
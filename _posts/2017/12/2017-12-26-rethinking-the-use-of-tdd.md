---
layout: post
title: Rethinking the use of TDD
categories: [Programming]
tags: [TDD, Jimmy Bogard, Kent Beck, Robert Martin, DDD, Terence McGhee]
date: 2017-12-26 05:00:00 PM UTC
published: true
---

<!-- December 27, 2017 01:00:00 AM Philippine Time -->

This is what Jimmy Bogard said in the conclusion of his talk, ["Crafting Wicked Domain Models" (NDC 2012)](https://www.youtube.com/watch?v=UYmTUw5LXwQ):

> DDD is all about building domain models that encapsulate the behavior.
<br /><br />
> So I'm not hiding behavior. I'm just saying it's up to the domain model itself to perform all these operations itself, and its gonna take care of its own. It defines its boundaries --- it does not let anyone do whatever it wants. It wraps up everyting nicely in a nice neat bowl.
<br /><br />
> **This is how I was able to eliminate bugs in our application a lot more easily than just writing a whole bunch of tests. Writing a bunch of tests still requires me to know how to write those tests, but in this case the domain model is offering me the right path.**
	
That last sentence makes me rethink the use of TDD in creating (almost) bug-free software.


<!--more-->


If you watch the video, Jimmy Bogard moved the business rules (or domain logic) from the `AssignOffer()` method into the entity classes.

The original `AssignOffer()` method (at about 16:00 mins in the video) looks like this:

``` csharp
public void AssignOffer(Guid memberId, Guid offerTypeId)
{
    var member = _memberRepository.GetById(memberId);
    var offerType = _offerTypeRepository.GetById(offerTypeId);

    var value = _offerValueCalculator.CalculateValue(member, offerType);

    DateTime dateExpiring
    switch (offerType.ExpirationType)
    {
        case ExpirationType.Assignment:
            dateExpiring = DateTime.Now.AddDays(offerType.DaysValid);
            break;
        case ExpirationType.Fixed:
            if (offerType.BeginDate != null)
                dateExpiring = 
                    offerType.BeginDate.Value.AddDays(offerType.DaysValid);
            else
                throw new InvalidOperationException();
            break;
        default:
            throw ArgumentOutOfRangeException();
    }

    var offer = new Offer
    {
        MemberAssigned = member,
        Type = offerType,
        Value = value,
        DateExpiring = dateExpiring
    };
    member.AssignedOffers.Add(offer);
    member.NumberOfActiveOffers++;

    _offerRepository.Save(offer);
}
```

Then it is transformed into this very simple method:

``` csharp
public void AssignOffer(Guid memberId, Guid offerTypeId)
{
    var member = _memberRepository.GetById(memberId);
    var offerType = _offerTypeRepository.GetById(offerTypeId);

    member.AssignOffer(offerType, _offerValueCalculator);
}
```

Wow! **Very easy to _read_!** (Please note that it was **_not_ easy to _write_** --- the transformation was not easy to do, I think, except maybe when you are a [_master_](https://terencemcghee.com/FileStore/Tech/1D0C454A70AC3AEF01BB1BAAD94C8753.html#guru) already, or a [_codesmith_](https://terencemcghee.com/FileStore/Tech/1D0C454A70AC3AEF01BB1BAAD94C8753.html#codesmith) at least. :smile:)

And the business rules are now moved to the entity (or the domain model) classes.

And the resulting entity classes look good! And they look **testable**! (Except, I think, on the part which uses `DateTime.Now`.)

Wow!

But he was not writing tests to guide him when transforming the entities! And, **_worse_**, he said that what he did was **easier** than writing a whole bunch of tests before doing any transformations!

_Oh no! Was Jimmy Bogard opposed to TDD??_

Maybe he was not... because the original code did not seem to have been written using TDD, because, first, he did not say that it has existing tests, and second, because it has a `DateTime.Now` in it...


``` csharp
    dateExpiring = DateTime.Now.AddDays(offerType.DaysValid);
```

... That would not be easy to test, because of the use of a static method (or a static readonly property in this case).

... I think if TDD was used to write the original code, the `DateTime.Now` should not have been there. Instead, there will be _something like_ a `DateService` object where we can get the dates from, like this:

``` csharp
    dateExpiring = 
        _dateService.GetDateTimeNow().AddDays(offerType.DaysValid);
```



So maybe Jimmy Bogard was _not_ opposed to TDD... 

Maybe he was opposed only to [writing tests _after-the-fact_](/memorabilia/videos/expecting-professionalism-by-uncle-bob-martin/#testing-legacy-code), that is, writing tests after the production code is already written, because that is hard to do (unless you are [Michael Feathers](https://www.bookdepository.com/Working-Effectively-with-Legacy-Code-Michael-Feathers/9780131177055?a_aid=jflaga) :smile:).


_Okay! Great!_

But if we can still come up with a good design even when we are not using TDD, **_maybe we do not need TDD at all!_** ([Except maybe when teaching good design](/2017/12/19/tdd-and-teaching-design-without-a-teacher))

Hmmmm...

Or maybe not... Maybe we still need TDD...

Because [TDD has other uses](/memorabilia/videos/expecting-professionalism-by-uncle-bob-martin/#advantages-of-tdd), such as giving us confidence when cleaning our code base, and having [examples to help others understand our code base](/memorabilia/books/the-craftsman-series/#8).

Kent Beck also, in his debate with DHH, said that the first reason why he writes tests first was to have fast feedback on whether what he is doing is correct or not. That is one of the advantages of writing the tests first: _fast feedback loop_.

In the end, I think, whether TDD is useful or not depends on the values being adopted by the members of a software team.


<!-- 

Adding to that is what Dijstra said about tests:

> "Testing shows the presence, not the absence of bugs."

What if we instead focus on 






Which of course Uncle Bob Martin also talked about in his book, Clean Architecture... Let's try look what he said...


> Dijkstra once said: "Testing shows the presence, not the absence of bugs." In other words, a program can be proven incorrect by a test; but cannot be proven correct. Therefore all that tests can do, after sufficient testing effort, is allow us to deem a program to be correct enough for our purposes.
<br /><br />
> The implication is stunning. Software development is not a mathematical endeavor; even though it seems to manipulate mathematical constructs. Rather, software is like a Science. We show correctness by applying our best efforts, and failing, to prove incorrectness.

(Oh! He quoted Dijkstra... I did not remember that...)





Having tests might also give us false assurance....

In the end, I think what needs to be changed is how software developers think about bug-free software --- "are going to do something to fix this?" or "all software has bugs, its still okay if our software also contains bugs"


Because, with what I know about TDD, we will not be having that DateTime.Now... but his code has that in there and it still looks good.


The essense of things: kend beck said that the first reason why he writes tests is so that there is fast feedback on whether what he is doing is correct or not.
 -->

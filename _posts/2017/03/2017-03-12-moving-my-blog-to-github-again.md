---
layout: post
title: Why am I moving my blog to GitHub! -- Again.
category: Miscellaneous
tags: [Blogging, Jekyll, Markdown]
date: 2017-03-12 02:40:00 PM UTC
excerpt_separator: <!--more-->
---
<!-- March 12, 2017 10:40:00 PM Philippine Time -->

<style type="text/css">
    li {
        list-style-type: none;
    }
</style>

## Reason #1: I want to be able to write blogs even when I don't have an internet connection
- Git solves this problem.["Most operations in Git only need local files and resources to operate..."](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)
<br /> <br />
I actually already [attempted last year to transfer my blog to GitHub](https://jboyflaga2.github.io/Transferring-blog-to-GitHub/) but I have choosen not to use it this time because it has a _weird_ name (just like my current blog -- refer to reason #4 below); and a friend of mine, Joash Tubaga, suggested that using _"jboy"_ for a name sounds childish; I should be using my real name. And I was convinced.

<!--more-->

## Reason #2: I want to be able to use emojis in my blog

- :sweat_smile: :+1: :musical_note:
<br /> <br />
:smiley_cat: :scream_cat: :dog:
<br /> <br />
:arrow_left: :arrow_right: :arrow_up:


## Reason #3: Writing code on GitHub flavored Markdown is simpler
- JavaScript code
``` javascript
    function test() {
        console.log("test");
    }
```

- C# code
``` csharp
    using System;

    public class Circle : Shape
    {
        private double radius;

        public Circle(double radius)
        {
            this.radius = radius;
        }

        public double Radius
        {
            get { return this.radius;}
            set { this.radius = value;}
        }

        override public double ComputeArea() 
        { 
            return Math.PI * Math.Pow(radius, 2);
        }
    }
```

## Reason #4: My current blog has a _weird_ name

- [jboyflaga2.blogspot.com](http://jboyflaga2.blogspot.com). Yes! With a _"2"_ at the end. It sounds unprofessional. :blush:
<br /> <br />
You want to know the reason why there is a _"2"_ in there?? It is because the one without the _"2"_ is already taken. I believe I was the one who made that blog years ago but I already deleted the google account assoiciated with it. But even if I did not delete it, I already forgot the password. :disappointed:
<br /> <br />
But my first blog, [jeremiahflaga.blogspot.com](http://jeremiahflaga.blogspot.com/2011/08/why-i-started-blogging.html), already uses my real name... only that reasons #1, #2, & #3 prevents me from using it also.
<br /> <br />
(I also attempted to create a blog named [teacherjboy.blogspot.com](http://teacherjboy.blogspot.com/), but its name sounds very controversial. :laughing::laughing::laughing: I cannot continue using it.)

<br />
You also want to move your blog to GitHub Pages? Check out this tutorial: [Build A Blog With Jekyll And GitHub Pages by Barry Clark](https://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/).

<br />
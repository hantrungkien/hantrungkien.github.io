---
layout: post
title: Some problems I encountered with my Jekyll powered blog -- and their solutions
category: Miscellaneous
tags: [Jekyll, Blogging, Timezones]
date: 2017-04-08 03:30:00 PM UTC
---

<!-- April 8, 2017 11:30:00 PM Philippine Time -->

This post wil be one of those [_"evolving publications"_](https://martinfowler.com/bliki/EvolvingPublication.html) as called by Martin Fowler.

But I will call this "_evolving notes_".

This post contains some of the problems I encountered while adding more functionality or fixing some errors to my Jekyll-powered blog.

<!--more-->

## Problem: Different URLs for different timezones

A few days ago, I noticed that Jekyll generates different URL's for different timezones.

For example, when I build my blog locally, it generates this URL:

> http://127.0.0.1:4000/2017/04/**06**/the-specific-generic-cycle-of-uncle-bob/

...because in my local machine the date is **April 6, 2017 01:05:00 AM**.

(Please **note** that I am using UTC as my publish date. For the example I am using, the UTC date is `2017-04-05 05:05:00 PM UTC`.)

But when I publish it to GitHub Pages, it generates a different URL:

> http://127.0.0.1:4000/2017/04/**05**/the-specific-generic-cycle-of-uncle-bob/

...because my local machine has this date & time: `April 6, 2017 01:05:00 AM`

**The solution** is to add `timezone: UTC` in `_config.yml`.

After that, when executing `jekyll serve --watch`, an error popped up.

```
jekyll 3.4.3 | Error:  No source of timezone data could be found.
Please refer to http://tzinfo.github.io/datasourcenotfound for help resolving this error.
```
I needed to install the gem `tzinfo-data`.

When I tried `gem install tzinfo-data -install-dependencies`, my machine installed it in the current folder instead of the folder where all the global gems are installed. (In my case, `C:\Ruby23-x64\lib\ruby\gems\2.3.0`)

So I googled and found that I needed to do this: `gem install tzinfo-data -include-dependencies --install-dir C:\Ruby23-x64\lib\ruby\gems\2.3.0`

That's it!


## Problem: How to add pagination

Just go to the docs [jekyllrb.com/docs/pagination/](https://jekyllrb.com/docs/pagination/)

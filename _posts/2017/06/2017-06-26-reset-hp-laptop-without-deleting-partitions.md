---
layout: post
title: How to reset/reformat HP Laptop (with Windows 10) without deleting user-created partitions
category: Miscellaneous
tags: [HP, Laptop, Windows 10, Disk Partitions]
date: 2017-06-26 09:50:00 AM UTC
---

<!-- June 26, 2017 05:50:00 PM Philippine Time -->

First of all be careful before you reset your HP laptop because the [HP Help page for this](https://support.hp.com/ph-en/document/c04758961#AbT2) has this warning:

> **WARNING:**
<br />
If the size of the OS partition (usually C:) was reduced below a minimum size requirement, other user-created partitions will be removed and stored data will be destroyed.

<span class="red-text">**You should backup your important files before doing the reset.**</span>

<!--more-->

## Some NOTES before doing the reset _(which might be related to the WARNING mentioned above)_: 

The first time I reset my HP Laptop with Windows 10, all the disk partitions that I created were lost, including all my files. But I'm thankful to God that I already have a backup to most of my files before that happened. So the bad effect was only minimal.

I was doing some _trial and error_ resetting so that I can find out how to reset my laptop without deleting my user-created partitions. (It took a lot of time :smile: but it will save me in the future.)

Twice did I encounter this error when I tried to **_shrink_** my system partition (C:) down to 300GB:

> You cannot shrink a volume beyond the point where any unmovable files are located. See the "defrag" event in the Application log for detailed information about the operation when it has completed.

I was only allowed to **_shrink_** it down to about 500GB.

If you have less than 500GB in your existing system partition (C:), <span class="red-text">please be sure to backup your files in your other partitions before you proceed, taking note of the _WARNING_ mentioned above. If you will (or cannot) backup your files, proceed at your own risk.</span>

_(I had about 800GB for my system partition (C:), and 100GB user-created partition, before I did the steps below.)_


## Steps

1\. Shutdown your laptop

2\. Turn on computer then repeatedly press F11

3\. Wait for the options to load

4\. Select "Troubleshoot"

5\. Select "Reset this PC"

![HP-reset-this-pc.png](/images/2017/HP-reset-this-pc.png)

6\. Select "Keep My Files"

![HP-keep-my-files.png](/images/2017/HP-keep-my-files.png)

7\. Wait... Click the "Next" buttons in the screens that follow until the screen below is shown:

![HP-ready-to-reset-this-pc.png](/images/2017/HP-ready-to-reset-this-pc.png)

8\. Click the "Reset" button... Wait for the computer to restart... Then follow the next instructions on the screen.

That's it!

Enjoy!

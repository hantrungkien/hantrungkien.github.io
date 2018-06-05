---
layout: post
title: How to shrink a disk volume beyond the point where any unmovable files are located
category: Miscellaneous
tags: [HP, Windows 10, Disk Partitions]
date: 2017-06-26 06:10:00 PM UTC
---

<!-- June 27, 2017 02:10:00 AM Philippine Time -->

When I tried to [reset my HP Laptop](/2017/06/26/reset-hp-laptop-without-deleting-partitions/) and tried to shrink my system partition (C:), _Windows 10_ did not allow me to shrink it down to 300GB. I was only allowed to shrink it down to about 500GB.

It had this error message:

> You cannot shrink a volume beyond the point where any unmovable files are located. See the "defrag" event in the Application log for detailed information about the operation when it has completed.

I googled for a solution and found this article by Mihai Neacsu: [How to shrink a disk volume beyond the point where any unmovable files are located](http://www.download3k.com/articles/How-to-shrink-a-disk-volume-beyond-the-point-where-any-unmovable-files-are-located-00432)

**I followed the instructions given in that article and I was able to shrink the system partition (C:) down to 300MB.**

![HP-system-partition.png](/images/2017/HP-system-partition.png)

<!--more-->

**Yehey!!**

I don't know yet if the forced shrinking of the system partition has side effects. One thing I noticed is that my system time does not adjust when I turn on the "Set time automatically" setting.

I will see in the next few days whether I encounter some unexpected errors. 

If I will encounter errors, then it will be time for the next experiment of _resetting HP Laptops_ --- I will try to see whether the **"Reset this PC but Keep my files"** option will retain my 300GB system partition, or whether it will delete all my partitions and reset the whole disk to factory settings.

... because the [Support page of HP](https://support.hp.com/ph-en/document/c04758961#AbT2) has this warning:

> **WARNING:**
<br />
> If the size of the OS partition (usually C:) was reduced below a minimum size requirement, other user-created partitions will be removed and stored data will be destroyed.

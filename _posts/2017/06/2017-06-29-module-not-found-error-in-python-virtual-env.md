---
layout: post
title: ModuleNotFoundError in a Python virtual environment
category: Programming
tags: [Python, virtualenv, ModuleNotFoundError, TDD with Python, TDD]
date: 2017-06-29 01:15:00 PM UTC
---

<!-- June 29, 2017 09:15:00 PM Philippine Time -->

Experiencing this error when you try to execute commands inside your Python virtual environment?

```
ModuleNotFoundError: No module named '<name of module>'
```

<!--more-->


I encountered it a while ago.

![python-ModuleNotFoundError.png](/images/2017/python-ModuleNotFoundError.png)

The reason might be because you transfered your virtual environment folder to another location (or you copied it from another computer, like in my case).

**This is how to fix it:**

1. Open the `/Scripts/activate` file inside your virtual environment folder.

2. Go to the line that has this (in my case, it is on line `#43`):
<br />
```
VIRTUAL_ENV="$(if [ "$OSTYPE" "==" "cygwin" ]; then cygpath -u 'Z:\<your NEW folder>'; else echo '/Z/<your NEW folder>'; fi;)"
```

3. Change the path to the new location of your virtual environment. :smile:
<br /> <br />
Change it from 
<br />
`Z:\<your OLD folder>` **and** `/Z/<your OLD folder>`
<br />
to 
<br />
`Z:\<your NEW folder>` **and** `/Z/<your NEW folder>`

4. If you are using the Command Prompt of Windows, you also have to change the path in the file `/Scripts/activate.bat`. (line `#2` in my case)
<br />
```
set "VIRTUAL_ENV=Z:\<folder>"
```
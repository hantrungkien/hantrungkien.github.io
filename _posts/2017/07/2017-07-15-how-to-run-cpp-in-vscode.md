---
layout: post
title: How to run single-file C++ code in Visual Studio Code on Windows 10
categories: [Programming]
tags: [C++, VIsual Studio Code, Windows 10, MinGW]
date: 2017-07-15 03:50:00 PM UTC
---

<!-- July 15, 2017 11:50:00 PM Philippine Time -->

NOTE: You should be connected to the internet until the end of these steps


## 1. Download and install a C++ compiler (if you don't have one yet installed in your machine).

**1.1.** Go to [www.mingw.org/](http://www.mingw.org/) and click the "Download Installer" button to download the MinGW setup file.

<!--more-->

**1.2.** Install MinGW and wait for the "MinGW Installation Manager" to show up. (see picture in step #3)

**1.3.** When the "MinGW Installation Manager" to shows up, click on the `mingw32-gcc-g++` then select "Mark for Installation"

![MinGW-Installation-Manager.png](/images/2017/MinGW-Installation-Manager.png)

**1.4.** In the menu at the top, click on "Installation" -> "Apply Changes"

![MinGW-installation-manager-apply-changes.png](/images/2017/MinGW-installation-manager-apply-changes.png)

**1.5.** Wait until the installation is finished

## 2. Edit your PATH environment variable to include the directory where the C++ compiler is located

![edit-environment-variables.png](/images/2017/edit-environment-variables.png)


## 3. Install "Code Runner" extension in VS Code

**3.1.** In VS Code, search for the extension called "Code Runner" then install it

![vscode-code-runner-extension.png](/images/2017/vscode-code-runner-extension.png)

**3.2.** Restart VS Code

**3.3.** Open you C++ file in VS Code

**3.4.** Run your code using "Code Runner"

From the docs of "Code Runner":

> Open code file or select code snippet in Text Editor, then use shortcut **`Ctrl+Alt+N`**, or press **`F1`** and then select/type **`Run Code`**, or right click the Text Editor and then click **`Run Code`** in editor context menu, or click **`Run Code`** button in editor title menu, the code will run and the output will be shown in the Output Window.

> To stop the running code, use shortcut **`Ctrl+Alt+M`**, or press **`F1`** and then select/type **`Stop Code Run`**, or right click the Output Channel and then click **`Stop Code Run`** in context menu



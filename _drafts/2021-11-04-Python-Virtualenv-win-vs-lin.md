---
layout: post
title: "Python Virtualenv: Windows vs Linux"
date: 2019-05-19 00:00:00 +0000
categories: blog
---

Although Virtualenv is available on both Linux and Windows, there are some differences that you may find useful to understand.

**Is there a difference to creating virtualenvs?**
No, creating virtualenvs in Windows and Linux is exactly the same.

**Can I use the same venv folder on both systems?**
No. You will need to create 2 separate virtual environments. I suggest creating folders named winvenv and linvenv to tell them apart. You will have access to the same packages through pip, although you will need to use pip freeze if you wanted to replicate the packages exactly.

**Do I activate the venvs in the same way?**
No, but you CAN activate, and the differences are subtle. After creating the virtualenv, follow these steps:

**Windows**

`\winvenv\Scripts> activate`

Navigate to Scripts within the venv root. Type **activate** to use your venv in the current prompt

**Linux**

`$ source ./linvenv/bin/activate`

In the terminal, type **source** followed by the path to /bin/activate within the viretualenv folder

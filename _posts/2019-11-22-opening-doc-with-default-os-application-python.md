---
layout: post
title: "Opening documents with default OS application in Python"
date: 2019-11-22
---

In [Chapter 15 of ABS](https://automatetheboringstuff.com/chapter15/), the author suggests the following for opening documents with default application in OS using Python:

`>>> import subprocess`\\
`>>> subprocess.Popen(['start', 'filename'], shell=True)`

When this didn't work for me, I searched for alternatives and found two that worked for me on a [Stack Overflow post](https://stackoverflow.com/questions/434597/open-document-with-default-os-application-in-python-both-in-windows-and-mac-os): 

`>>> import subprocess`\\
`>>> subprocess.run(['open', 'filename'], check=True)`

`>>> import os`\\
`>>> os.popen('open filename')`

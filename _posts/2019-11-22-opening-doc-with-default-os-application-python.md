---
layout: post
title: "Opening documents with default OS application in Python"
date: 2019-11-22
---

In Chapter 15 of ABS, the author suggests the following for opening documents with default application in OS using Python:
`>>> import subprocess`\\
`>>> subprocess.Popen(['start', 'filename'], shell=True)`

When this didn't work for me, I searched for alternatives and found two that worked for me: 
`>>> import subprocess`\\
`>>> subprocess.run(['open', 'filename'], check=True)`

`>>> import os`\\
`>>> os.popen('open filename')`

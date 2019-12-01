---
layout: post
title: "Fixing CERTIFICATE_VERIFY_FAILED error when using imapclient on OSX"
date: 2019-10-01
---

Post coming soon describing my experience: 
[Chapter 16: Sending Email and Text Messages](https://automatetheboringstuff.com/chapter16/)
Using imapclient library, needed to create IMAP object using: imapObj = imapclient.IMAPClient('imap.gmail.com', ssl=True)
This produced error [SSL: CERTIFICATE_VERIFY_FAILED].
Turns out that many others have run into this, not only with imapclient.
Python doesn't include its own SSL certificates. They need to be imported. One way to do so is using the 'Install Certificates.command' file that is in file with Python.
Running it by double-clicking in folder didn't work. 
To run in the command line, I copied folder path and pasted it into terminal with cd --> cd /Applications/Python\ 3.7
I used cat command to see contents of the install certificates file and saw it was a Python file.
Running it as /Install\ Certificates.command didn't work because I didn't have sufficient permissions, so I ran as sudo ./Install\ Certificates.command 
That worked! Once I did that, I was able to create imapObj and proceed. 

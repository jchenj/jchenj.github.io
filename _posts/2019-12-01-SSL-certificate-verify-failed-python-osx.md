---
layout: post
title: "Fixing SSL: CERTIFICATE_VERIFY_FAILED error when using imapclient on OSX"
date: 2019-12-01
---

Notes for full post coming soon: <br>
[Chapter 16: Sending Email and Text Messages](https://automatetheboringstuff.com/chapter16/)<br>
Using imapclient library, needed to create IMAP object using:<br>
`>>> imapObj = imapclient.IMAPClient('imap.gmail.com', ssl=True)`<br>
This produced an SSL: CERTIFICATE_VERIFY_FAILED error.<br>
Turns out that many others have run into this, not only with imapclient. <br>
Python doesn't include its own SSL certificates. They need to be imported. One way to do so is using the 'Install Certificates.command' file that is in file with Python.<br>
Running it by double-clicking in folder didn't work. <br>
To run in the command line, I copied folder path and pasted it into terminal:
`jchen@ribka:~/Applications$ cd /Applications/Python\ 3.7`<br>
I used the cat command to see contents of the install certificates file and saw it was a Python file.<br>
Running it as /Install\ Certificates.command didn't work because I didn't have sufficient permissions, so I ran as a super user:
`jchen@ribka:~/Applications$ sudo ./Install\ Certificates.command`<br>
That worked! Once I did that, I was able to create imapObj and proceed. <br>
(Another way is to get SSL certificates for Python with OSX is to download the certifi package from pip. I already had certifi - presumably if I had just updated it, that would have worked as well.)

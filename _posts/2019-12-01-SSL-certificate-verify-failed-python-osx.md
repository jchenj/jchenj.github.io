---
layout: post
title: "SSL: CERTIFICATE_VERIFY_FAILED error when using imapclient on OSX"
date: 2019-12-01
---

While working through [Chapter 16: Sending Email and Text Messages](https://automatetheboringstuff.com/chapter16/) of *ABS* I ran into an issue using the `imapclient` library. 

To retrieve emails using IMAP, the first step after downloading the library was given as creating an IMAP object with:

`>>> imapObj = imapclient.IMAPClient('imap.gmail.com', ssl=True)`\\

However, this produced an SSL: CERTIFICATE_VERIFY_FAILED error.

I quickly found that others have run into this issue, and not only with `imapclient`. I learned that Python doesn't include its own SSL certificates; they need to be imported. One way to do this is to run the `Install Certificates.command` file that is downloaded along with Python.

When I tried running this by double-clicking the file, it didn't work. So I navigated to the file in the command line by copying the Python folder path and pasting it in the terminal: 

`jchen@ribka:~/Applications$ cd /Applications/Python\ 3.7`\\

I used the `cat` command to see contents of the `Install Certificates` file and saw it was a Python file. Running it with `"/Install Certificates.command"` didn't work because I didn't have sufficient permissions, so I ran as a super user:

`jchen@ribka:~/Applications$ sudo "./Install Certificates.command"`

That worked! Once I did that, I was able to create my `imapObj` and proceed with logging into an IMAP server, searching and fetching emails. 

(I read that another way is to get SSL certificates for Python with OSX is to download the `certifi` package from `pip`. As I already had `certifi` loaded, presumably if I had just updated it, that would have worked as well.)

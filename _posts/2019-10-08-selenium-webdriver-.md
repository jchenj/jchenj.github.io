---
layout: post
title: "A beginner-friendly way to import a web driver for Selenium"
date: 2019-10-08
---

While working through the webscraping chapter of Automate the Boring Stuff (ABS) with Python, I ran into an early snag when it came to launching a browser. According to the book's instructions, the first step is to import the Selenium web driver by entering the following:

`>>> from selenium import webdriver`
`>>> browser = webdriver.Firefox()`

This failed, producing a long error message. I searched online for the cause of the problem and soon found it: As of Firefox 47 - released in 2016 - the Selenium WebDriver has been deprecated, and users must download and use a third-party web driver. 

I'm currently running Firefox version 69, this is an issue that has clearly been around for a while, and at least one other ABS reader has had the same difficulty as I owing to the outdated instructions.

The responses to Stack Overflow questions about this issue gave me a pretty clear idea of what needed to be done. Firefox would have needed download and setting path, parameters, etc - complicated! 
Instructions for chrome driver were easier
I saw I have chrome 77 - so downloaded corresponding chrome driver
I put driver on Desktop and put path to driver as parameter in web driver.chrome()

Overall, I've found Automate the Boring Stuff a fantastic book for getting started with Python. It was published in 2015, so 


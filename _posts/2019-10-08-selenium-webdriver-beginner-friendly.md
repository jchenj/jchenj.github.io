---
layout: post
title: "A beginner-friendly way to import a web driver for Selenium"
date: 2019-10-08
---

While working through the webscraping chapter of *Automate the Boring Stuff with Python*, I ran into an early snag when it came to launching a browser. According to the book's instructions, the first step is to import the Selenium web driver by entering the following:

`>>> from selenium import webdriver`\\
`>>> browser = webdriver.Firefox()`\\

This failed, producing an error message. I searched online for the cause of the problem and soon found it: As of Firefox 47 - released in 2016 - the Selenium WebDriver has been deprecated, and users must download and use another web driver. 

As ABS was published in 2015, the book's instructions were make outdated by this change. Since this complication has been around for a while, I was able to take advantage of those who had already dealt with it. Back in 2016, a fellow ABS reader had the same difficulty as I did owing to the book's instructions being outdated, and posted a [question to Stack Overflow] (https://stackoverflow.com/questions/37966050/automate-the-boring-stuff-with-python-outdated-instructions-for-launching-seleni) The response to that post presented two clear options: 1) download a separate webdriver or 2) downgrade my Firefox version. 

I wasn't keen on the idea of downgrading Firefox, so looked more closely at the process for downloading a new webdriver. While the post response recommended using the Gecko Marionette Firefox Driver, I had two issues with this. For one, the [Mozilla documentation] (https://developer.mozilla.org/en-US/docs/Web/WebDriver) seemed incomplete. In addition, a [second set of instructions] (https://stackoverflow.com/questions/37761668/cant-open-browser-with-selenium-after-firefox-update) - provided in response to another Stack Overflow post of essentially the same question - was more complex that I was immediately able to implement. While I recognize that I'll need to learn to set a download's location to the Python path, for now I just wanted to get a new driver set up to work with Selenium as soon as possible!

I checked to see whether Chrome has a web driver, and sure enough, I found the [ChromeDriver] (https://sites.google.com/a/chromium.org/chromedriver/). The [instructions] (https://sites.google.com/a/chromium.org/chromedriver/getting-started) for ChromeDriver were much more straighforward: I checked my current Chrome version (77) and downloaded the corresponding ChromeDriver version. I put the downloaded driver on my desktop. The only other thing I needed to do was to include the path to ChromeDriver when instantiating webdriver.Chrome parameter in webdriver.chrome() by entering:

`>>> from selenium import webdriver`\\
`>>> browser = webdriver.Chrome('/Users/jchen/Desktop/chromedriver')`\\

Once I did that, I was able to follow the further instructions in *Automate the Boring Stuff* to open a browser window and proceed with adventures in webscraping. While this issue took a little time to figure out, the helpful takeaway for me was to look closely at possible solutions to an issue, try to understand their tradeoffs, and to feel free to go with the solution that I am most comfortable with given my current skill leve (all else being equal.)

One final note: Overall, I've found *Automate the Boring Stuff* a fantastic book for getting started with Python. The [second edition] (https://automatetheboringstuff.com) is scheduled to be released in late October 2019, and hopefully will include updated instructions for using Selenium. 


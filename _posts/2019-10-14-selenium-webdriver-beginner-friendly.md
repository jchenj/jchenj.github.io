---
layout: post
title: "A beginner-friendly way to import a web driver for Selenium"
date: 2019-10-14
---

While working through [Chap. 12 on web scraping](https://automatetheboringstuff.com/2e/chapter12/) in *Automate the Boring Stuff with Python* (1st edition, 2015), I ran into an early snag when it came to launching a browser. According to the book's instructions, the first step is to import the Selenium web driver by entering the following:

`>>> from selenium import webdriver`\\
`>>> browser = webdriver.Firefox()`

When this failed, producing an error message, I searched online for the cause of the problem and soon found it: as of Firefox 47 - released in 2016 - the Selenium WebDriver has been deprecated, and users must download and use another web driver. 

Since this complication has been around for a while, I was able to learn from those who had already dealt with it. Back in 2016, a fellow ABS reader had the same difficulty as I did owing to the book's outdated instructions and posted a [question to Stack Overflow](https://stackoverflow.com/questions/37966050/automate-the-boring-stuff-with-python-outdated-instructions-for-launching-seleni) The response to that post presented two options: 1) download a separate web driver or 2) downgrade my Firefox version. 

I wasn't keen on the idea of downgrading Firefox, so I looked more closely at the process for downloading a new web driver. While the post response recommended using the Gecko Marionette Firefox Driver, I encountered two issues with this. First, the [Mozilla documentation](https://developer.mozilla.org/en-US/docs/Web/WebDriver) seemed incomplete. In addition, a [second set of instructions](https://stackoverflow.com/questions/37761668/cant-open-browser-with-selenium-after-firefox-update) - provided in response to another Stack Overflow post of essentially the same question - was more complex than I was immediately able to implement. While I'll be looking to learn how to set a download's location to the Python path, for now I just wanted to get a new driver set up to work with Selenium as soon as possible. 

Looking for an alternative to the Firefox driver, I checked to see whether Chrome has one, and sure enough, I found the [ChromeDriver](https://sites.google.com/a/chromium.org/chromedriver/). The [instructions](https://sites.google.com/a/chromium.org/chromedriver/getting-started) for ChromeDriver were much more straighforward: I checked my current Chrome version (77) and downloaded the corresponding ChromeDriver version to my desktop. I then only needed to include the path to ChromeDriver when instantiating webdriver.Chrome by entering:

`>>> from selenium import webdriver`\\
`>>> browser = webdriver.Chrome('/Users/jchen/Desktop/chromedriver')`

Once I did that, I was able to continue followingt the instructions in *Automate the Boring Stuff* to open a browser window and proceed with my adventures in web scraping. 

While this issue took a little time to figure out, the takeaway for me was that once I've looked closely at possible solutions to an issue and understood their tradeoffs, I can feel free to implement the solution that I am most comfortable with given my current skill level. 

One final note: Overall, I've found *Automate the Boring Stuff* a fantastic book for getting started with Python. The second edition is scheduled to be released in late October 2019, and hopefully will include updated instructions for using a web driver with Selenium. 

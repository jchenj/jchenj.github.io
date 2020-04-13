---
layout: post
title: "PyTest Usage"
date: 2020-04-12
---

This week I've gotten back into my course on web development with Python and have been building an API using API Star. I had a quick teachable moment after I finished writing the API, write the first test function and ran the test file for the first time.

The test file ran successfully, but no info about test outcomes appeared in the terminal window. I tried again a couple of times, and was really scratching my head about why I wasn't seeing the output I was expecting. I had run tests in pytest when I last worked on this topic a few weeks ago, and I've been testing extensively with unittest more recently. What could be the issue now? 

After a minute or so puzzling over this, I ran a search for 'running tests pytest' and pulled up the pytest Usage & Invocations page and quickly found my error. To run tests in a module with pytest, like I was doing, one runs `pytest <test_mod.py>` I had been running `python3 <test_mod.py>` because this is how it's done in unittest.

I ran the test file again with the correct usage, and the tests ran successfully, outputing expected info on test results. 

A few reminders & learning I gained from this experience:
* Reminder that assumptions can be misleading on module usage. Two modules that "do the same thing" can still have significant differences in their usage. 
* At the same time, using assumptions about how similar modules work can be a fine starting point for using a new module. I should just be prepared to check documentation and other resources if it turns out that these assumptions aren't valid. 
* Finally, it's a good idea to monitor roughly how long I've spent trying to understand an issue on my own before looking to docs & resources. For a relatively small issue like the one I dealt with today, if I haven't hit on the solution in a few minutes, it's probably a good idea to check other resource to solve the issue, learn from it and move along. 

#! TODO: link to API repo / course page
#! TODO: link to pytest page
Pytest usage: https://docs.pytest.org/en/latest/usage.html

---
layout: post
title: "Debugging"
date: 2020-04-14
---

A few situations in recent days have highlighted that I have a lot to learn yet about debugging. Happily, one situation resulted in lots of good learning that I think will smooth the debugging process for me overall, I think.

I was working on my password manager program, specifically on a function to encrypt a given file's data. The function takes the data as a parameter, in the form of a list of lists. The data is output by the `_readFile()` function that is called before `_encryptData()` 

At a certain point in writing the new function I wanted to check the output of the `data` variable from `_readFile()`. It was clear to me that I wanted to run the program, call the function and check the value of `data` but even after all the ways I've worked with debugging so far - using PyCharm's debugging tools, the `breakpoint()` function, using `print()` statements - I wasn't sure what was the best way to go about this. 

I had a feeling that I should put a breakpoint in - but where? And how would I check the value of `data`? I asked for some help in understanding the principles at work here and learned the following:

* Put a breakpoint in the function that I'd like to debug (in the main program). Ideally the breakpoint should be near the area of the function that I'm interested in (e.g. where the value of `data` is assigned). 
* If I have tests written, run a test in debug mode that calls the function with the breakpoint. (Since I do have tests for the password manager, this is the option I went with.)
* Once the program stops at the breakpoint, I can step through using the debugger to see changes in variable values, etc. 
* If I don't have tests, I can set up a new run configuration and run the program using it to see the behavior under the specified conditions. Running with tests seems preferable. 

While I know there's many more tools & approaches to learn for debugging, these pointers were very helpful. I was able to check the output of the `_readFile()` function using a breakpoint, and continue on my way!
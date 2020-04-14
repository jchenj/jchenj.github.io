---
layout: post
title: "Debugging"
date: 2020-04-14
---

Situation - transforming list of lists to string. Wanted to see output of data. 
Task - needed to run program and see contents of data var
Action - realized debugging needed. Put a breakpoint and run - but where to put pb? How to check output? 

Asked for clarification and got it. 
Put a breakpoint in func I'd like to test, near the part I'm interested in. 
Since I have tests, run a test that calls that func. 
Once program stops at the breakpoint, step through to see changes in values. 
If I didn't have tests, I could set run config and run prog using that config
I could also used breakpoint() and likely other tools I don't yet know about to check the results of funcs. 

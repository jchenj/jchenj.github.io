---
layout: post
title: "Refactoring file operations into new class"
date: 2020-04-30
---

Finished major refactoring in passman. 

Why? Had just one class, Account. Included several funcs that were not related to account but more properly the file.

What did - create a new class, PwFile, to put these funcs into. 
Also needed to update Account funcs to take pwfile as a parameter. 
Also needed to check, revise command line args, check with integration tests and unit tests. Needed to rewrite quite a few unit tests/  

What new experiences did I get? 
- Added type hints to all funcs
- Saw how helpful it was to have docstrings
- Learned that good to focus on one bit of refactoring at a time. I was interested in possibly refactoring to make new AccountList class alongside Account. Got good advice to complete one refactoring before starting on this

What challenges did I encounter? 
-When I renamed funcs or params, took while before I made change in all places
- Global variable 0 in the test I needed to set it  - and also needed to invoke with `global pyfile` to make clear that I was referring to and modifying it
- For create_new_file() needed to move it up in the command line commands

What did I learn from the experience? 
Took both longer than expected & less time. Lot of details and bug checking. On the other hand, I didn't have to touch all code - many funcs didn't have to work with, and didn't have to change most or CL args and integration tests at all. Overall satisfying process and great outcome that program architecture makes more sense, and more flexible for future work. 
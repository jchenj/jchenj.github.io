---
layout: post
title: "Design patterns"
date: 2020-04-20
---

Situation: Original change password func only allowed for a randomly generated password. Wanted to have an option to set the password

Task: Refactor the change_password() function

Action: Considered some options, extending the change_pw function. Basically adding some additional conditions. Saying if only the password parameter was set, then to set with that specific pw. Otherwise, if alphabet and pw length were given, to autogenerate random password

Learned that there was a cleaner way to do this, using design pattern. 
Separate the setting of password (either spec or random) from the changing of file with new pw. Ended up pulling out a func for change_pw and writing two new funcs for set_pw_rand and set_pw (specified)

How did I refer to these funcs in the main func? 

And what happened when it came time to refactor 'add_account' to allow a specified func? 
   Thought about adding same design pattern, but didn't need to 
   With just two additional lines of code in main func, said if there's a setpw param, then can setpw with it
   This was lot shorter and possible because I had already pulled out that fun
   
I've heard a lot about design patterns - this was first experience using one. Will be interesting to learn what this is called, and learn more examples

Result
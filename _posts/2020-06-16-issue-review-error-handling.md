---
layout: post
title: "Issue review: Error handling in ezpass - Day 1'"
date: 2020-06-16
---

I just closed an [issue](https://github.com/jchenj/ezpass/commit/de9274752f902149e7525117de422b392f04cbb2)
 in my password manager project that was super instructive. When I started
  working on it, I thought it would take just a few lines of code to solve
  . It turned into a much more extensive effort that touched code I didn't
   expect at all. I'm documenting my approach and a few of the key takeaways
    here, breaking into separate entries for each day. 
    
## Problem
Issue #77 described how user errors related to password entry were handled in an
 ugly way. If a user entered the wrong password to open an encrypted file, 
 the program crashed and she got a long, unhelpful traceback message. 
 
 
 While the issue only  mentioned this problem, I knew that there were other
   difficulties with password entry. If a user entered the `--no-encrypt` flag 
   when the file was in fact encrypted, the program would also crash and
    produce a long traceback. Most awfully, in interactive mode, a user could
     enter the wrong password for an encrypted file and still proceed to
      access the file! 
      
## Approach - Day 1
I started out focusing on the specific scenario described in the issue: the
 user had attempted to get the password for a specified account, but ran into
  problems because they entered the wrong password. The main function
   handling around the `getacpass` flag had been:
   
   ````python 
    if args.get_acpass is not None:
        account = Account(pfile, args.get_acpass)
        account.get_password_from_file(args.print_to_screen)
        if args.print_to_screen is False:
            print("Password for account '{}' in paste buffer".format(
                args.get_acpass))
````

I updated this to catch the error thrown by entering an incorrect password
 and printing a short message to the user. 

````  python
 if args.get_acpass is not None:
        account = Account(pfile, args.get_acpass)
        try:
            account.get_password_from_file(args.print_to_screen)
        except cryptography.fernet.InvalidToken as e:
            print("Error: incorrect file password. Please try again")
            sys.exit(1)
        if args.print_to_screen is False:
            print("Password for account '{}' in paste buffer".format(
                args.get_acpass))
````

I then turned to interactive mode specifically. I needed to catch this error
 right as the user starts the program. At this point, interactive mode
  started up with:
 
 ```python
    if args.interactive is True:
        shell = PassShell(pfile)
        shell.cmdloop()
        return

```
I wanted to check the password right here, and the best idea I came up with
 for how to do this was to try reading in the file before creating the shell
  instance & throwing an error if `readFile` failed:
 
 ```python
    if args.interactive is True:
        #! TODO: try to read file here & request password again if not correct?
        #! TODO: figure out how to have prog continue instead of exit
        #! TODO: also, is there better way than trying to read file here?
        try:
            pfile.readFile()
        except cryptography.fernet.InvalidToken as e:
            print("Error: incorrect file password. Please try again")
            return
        shell = PassShell(pfile)
        shell.cmdloop()
        return
```
 
Problems remained, though:
1) I wanted the program to inform the user of the password error and prompt
 to try again, rather than ending the program. 
 2) I wasn't sure that trying to read in the file was the right approach. It
  seemed like too much to do just to verify the password, especially since my
   code isn't set up to make use of the data read in at this point. Also, I wondered if
   there was a security risk caused by having the data read in and floating
    around in memory without being called and used. 
    
I'd come back to this in day 2!
    
## Key principles learned/reinforced
* Start work on an issue by attempting to replicate the described behavior
* Got better at reading stack traces - starting at the beginning, look for
 first time the error shows up in my code. 
* Clarified distinction between where error is caught & where it's handled
* Started to become aware of considerations around where's best to handle an
 error / which functions are best equipped to handle them 
 
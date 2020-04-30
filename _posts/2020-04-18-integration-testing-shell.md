---
layout: post
title: "First steps to integration testing using shell scripts"
date: 2020-04-17
---

Now that the password manager program includes quite extensive unit testing, today I started working on adding integration testing. 
 
 I did this by writing a shell script that runs through a sequence of program commands exactly as if I were entering them in the command line. 
 
Until now I've mostly used Bash to run individual commands from the terminal. This was my first experience writing a shell script for testing. 

Writing the script was pretty straightforward. It starts with the ```#!/bin/bash``` line, similar to what I used when I wrote Python programs in IDLE and ran them from the terminal. 

(Also similar to this early Python experience, to make the script runnable I needed to enter `chmod +x <filename>` before running it for the first time. After that, I can run the script using one of:

`./script-name.sh`
`sh script-name-here.sh` or
`bash script-name-here.sh`

The equivalent to Python `print()` statements is `echo <message>` in Bash. I used a couple of these at the start and end of the script.

The bulk of the script consists of the sequence of commands:

````python
# Create new file
  python3 passman.py -f testfile -nf
# Create new account
  python3 passman.py -f testfile -na bob
# Get password for account
  python3 passman.py -f testfile -g bob
# Change password, specifying password length
  python3 passman.py -f testfile -cp bob -l 4
# Change password with specified password
  python3 passman.py -f testfile -cp bob -sp 8080boat
# Get password, printing to screen
  python3 passman.py -f testfile -g bob -print
#! Delete account
  python3 passman.py -f testfile -d bob
````

It was important to removed the testfile at the end of the sequence (`rm testfile`), because the test will throw an error if it goes to create the file the next time and finds a file with the same name already exists. 

In order to make the shell script runnable 

So far the integration tests are only for unencrypted files. In order to test encrypted files< I'll need to be able to supply the password when prompted by the prgram. I could do this manually or by storign the passwords in a separate file and piping them in when prompted. I will address this in the future. For now, integration for the unencrypted files is working! 
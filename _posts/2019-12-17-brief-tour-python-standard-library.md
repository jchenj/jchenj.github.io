---
layout: post
title: "Brief Tour of the Standard Library"
date: 2019-12-17
---

Today I started working through Chapter 10 of the Python Tutorial (3.7.5), *Brief Tour of the Standard Library*. 


I have already used the following modules from the standard library by completing through half of Chapter 16 of *Automate 
the Boring Stuff with Python*:


* copy
* csv
* datetime
* json
* logging
* math
* os
* pprint
* random
* re
* shelve
* shutil
* smtplib
* sys
* threading
* time
* traceback
* webbrowser
* zipfile


That's nineteen modules so far - and I might have used a few more when working through other tutorials, etc. 


By going through this section, I'm looking forward to: 

1. Learn about modules I haven't encountered yet
2. Learn more about modules I have used before, and 
3. Learn more about the history, structure and future prospects for the standard library


---
# What I learned about:

## New (to me) modules:
### argparse
* argparse provides more sophisticated ways tow work with command line arguments than sys.argv

### doctest
* This module can scan another module and validate the tests embedded in a program's doctstring
* To work, there need to be three angle brackets in front of the call. (e.g. >>> print(average(\[20, 30, 50])

### glob
* glob.glob(*pathname*) returns a list of all pathnames in the current working directory that match the specified pattern.

### statistics
* The statistics module calculates various basic statistical properties (e.g. mean, median, variance) of a given list of numeric data

### timeit
* This module is used for performance measurement 

### urllib.request
* The requests module provides the same functionality as this module, I think, but is easier to use

### zlib
* This is a module for data compression.
* zlib.compress(*data, level*) takes a byte-like object for the data, not a string. To make a bytes-like object from a string, put a 'b' in front of the string. (e.g. s = b'This will produce a bytes-like object')


## Modules I'd used before:
### os
* This is one of the modules I've been using most frequently, especially os.getcwd() and os.chdir()
* Before today I haven't known how to specify the new desired path in os.chdir() using a relative path. Today I learned how to do this. os.chdir(*'./folder-name'*) changes the current working directory (CWD) to the specified folder within the current directory. os.chdir(*'../folder-name'*) changes the CWD to the specified folder within the parent folder of the current directory.
* I clarified that for relative paths there are only *dot* (.) and *dot-dot* (..) folders. I had thought that there could be an arbitary number of dots - e.g. *dot-dot-dot* (...) - but this is not true, at least from what I see looking back at *ABS*.
* os.system(command) - Executes the command (which is a string) in a subshell. This is still unclear to me. What's a subshell? 
* Reminded to use dir(*module-name*) to get a directory of all functions in a module, and help(*module-name*)to get a manual page from the module's docstring.

### random
* The function random.choice(*[list]*) chooses a random value from the given list.

### re
* String methods are preferred to re for simple tasks because they are easier to read and debug

### shutil
* For daily file & directory management, shutil is easier to use than os 

### sys
* The most direct way to terminate a script is sys.exit()


## History, structure & future prospects of the Python standard library:

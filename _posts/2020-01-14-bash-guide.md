---
layout: post
title: "Intro to Bash"
date: 2020-01-14
---

Notes on [The Bash Guide: A quality driven guide through the shell's many features](https://guide.bash.academy/#toc0)

### Key new terms (all chapters)
* **append mode** - file's original content is retained and new stream's bytes are added to it. E.g. `echo World >>~/world`
* **builtin** - small operations built into bash
* **byte** - unit of digital info; eight bits
* **compound command** - several basic commands grouped into a larger logical block (e.g. an *if* command)
* **control operator** - tells bash how preceding command should be executed. (Comes after command in list of commands.) (e.g. ';' means start a new line, '||' means run subsequent command only if preceding command failed
* **duplicating file descriptors** - copying one FD's stream connection to another FD. Use the `>&` operator, preceded by FD to change and followed by FD whose stream to copy
* **file descriptor (FD)** - "plug" to connect processes to files, devices or other processes. They are identified by numbers. The first three have standard names:

0 - standard input (e.g. keyboard). \\
1 - standard output (e.g. window within display). Redirecting FD1 is done with `>` operator.\\
2 - standard error (where errors & info messages are sent to - e.g. also display)\\

* **array** - parameter that can hold a list of strings
* **kernel** - the core part of the computer's operating system, and has control over everything else in the system
* **PATH** - an environment variable that contains a set of directories that should be searched for programs. The PATH variable can be updated. 
* **pipeline** - connect two commands by the linking the first process' standard output to the second's standard input
* **positional parameters** - parameters with a number - e.g. $1 - where the number is the argument number
* **redirections** - operations that change the source or destination of a file descriptor (e.g. write the result of a command to a file instead of to the terminal display). Redirecting standard output (FD1) to a file is most common redirection. Redirect any FD by prefixing the `>` operator with the number of the FD (e.g. `2>` to redirect standard error). Redirections are evaluated from L to R.
* **shell internal variables** - shell variables created automatically by the bash shell. They are in ALL CAPS. 
* **simple commands** - specifies name of command, with optional arguments, environment variables and file descriptor redirections
* **streams** - flows of info (bytes) between files, devices & processes
* **terminal multiplexer** - program that can run several login sessions in the same terminal window 

### Important commands (all chapters)
* `bash` - start  bash in most shells/terminals (if it's not already running)
* `cat [filename]` - show contents of file
* `cp` - copy a file
* `chmod +x [filename]` - marks a file as executable
* `coproc` - allows you to run a command asynchronously ('in the background')
* *CTRL-C* - stops running process 
* `echo "$BASH_VERSION` - check what version of bash currently running
* `expansions` - e.g `$variable` or `$(command)` - TO BE COMPLETED
* `fi` - closes an if statement and starts the command
* `rev` - reverses a string/line
* `type \[name]` - returns the location of the specified program \[name]

### Important switches (all chapters)
[List of swiches](https://www.tldp.org/LDP/abs/html/options.html)
* `-a` - show all the possibilities
* `-c` - copy from a string

### What to follow up on (all chapters)
* More practice with adding/removing items from the PATH
* More practice with file descriptor redirections 
* **Here documents** - better understand (something about making FD0 Standard Input read from document between two delimiters)
* **Here string** - understand use of (making FD0 Standard Input read from string between two delimiters)

### Ch. 1: Inception - What is bash and where does it live? 
* Each shell program has its own language
* A binary is an executable program that contains binary code executed by the system's kernel
* Windows doesn't come with bash installed
* Terminals programs are actually "terminal emulators", and there are many different ones available
* Bash is only one of many programs that can run in the terminal
* When a program is run, the system creates a running process for it. Processes have plugs (file descriptors) that allow them to connect streams that lead to files, devices or other programs

### Ch.2  Commands & Arguments
* Most command execution in bash is synchronous - one command must finish executing before it will execute the next command 
* The hashbang line at the top of a bash script `/usr/bin/env bash` commands the `env` program to find the `bash` program 
and use it for interpreting the language in the script
* Bash is not a strict interpreter. As a result, many bash scripts are buggy.
* Variable assignments go before a command name and apply to the enviroment of the one command only
* There are different kinds of commands (e.g. simple & compound)
* Braces (`[ ]`) join everything within them into a single compound command
* For delaring functions in bash, the function name is followed by empty parens - e.g. exists()
* Bash only does a `PATH` search on command names that don't contain a `/` character
* Two ways to make characters literal: quotation marks (preferred) and escaping
* Use double-quotes in args with expansions, single quotes everywhere else
* QUOTING ISSUES ARE THE CAUSE OF MANY BASH PROBLEMS. IF THERE IS WHITESPACE OR A SYMBOL IN AN ARG, USE QUOTES AROUND IT!
* To discard unwanted error messages, stream them to the `null` device - `2>/dev/null`
* To send both output and error bytes to a file, need to make sure they're on the same stream by duplicating file descriptors

### Ch. 3 - Variables & Expansions
* Lost notes from the first half of the chapter :( 
* Shell variables are stored in the process environment 
* Environment varibales are more general than shell variables
* Users can modify/add to both shell & environment variables
* All processes share environment varaibles. Some programs only use some of them. 
* Use single quotes to wrap strings (not double)
* Use `\` to resume on a new line
* Give your own shell variables lowercase names & environment variables uppercase
* Important to include space in front of negative start values

### Tests & Conditionals


### Loops & Functions

### Asynchronous Commands

### Colors & Terminal Commands

### Customizing the Prompt

### Advanced Topics

### Recommendations & Pitfalls

### Noteworthy External Tools

### General notes
* To run a bash script, looks like one can use `bash [file] [args]` or `[file] [args]`

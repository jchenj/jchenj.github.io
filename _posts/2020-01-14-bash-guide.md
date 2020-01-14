---

---

Notes on The Bash Guide: A quality driven guide through the shell's many features https://guide.bash.academy/#toc0
### Important commands (all chapters)
* `bash` - start  bash in most shells/terminals (if it's not already running)
* `cat [filename]` - show contents of file
* 'chmod +x [filename] - marks a file as executable
* `echo "$BASH_VERSION` - check what version of bash currently running
* `fi` - closes an if statement and starts the command

### Key new terms (all chapters)
* byte - unit of digital info; eight bits
* Compound Command - several basic commands grouped into a larger logical block (e.g. an *if* command)
* file descriptors - "plugs" to connect processes to files, devices or other processes. They are identified by numbers. The first
three have standard names:
** 0 - standard input (e.g. keyboard)
** 1 - standard output (e.g. window within display)
** 2 - standard error (where errors & info messages are sent to - e.g. also display)
* kernel - the core part of the computer's operating system, and has control over everything else in the system
* streams - flows of info (bytes) between files, devices & processes
* terminal multiplexer - program that can run several login sessions in the same terminal window 

### Ch. 1: Inception - What is bash and where does it live? 
** What was new / interesting? **
* Each shell program has its own language
* A binary is an executable program that contains binary code executed by the system's kernel
* Windows doesn't come with bash installed
* Terminals programs are actually "terminal emulators", and there are many different ones available
* Bash is only one of many programs that can run in the terminal
* When a program is run, the system creates a running process for it. Processes have plugs (file descriptors) that allow them to 
connect streams that lead to files, devices or other programs

### Ch.2  Commands & Arguments
** What was new / interesting? **
* Most command execution in bash is synchronous - one command must finish executing before it will execute the next command 
* The hashbang line at the top of a bash script `/usr/bin/env bash` commands the `env` program to find the `bash` program 
and use it for interpreting the language in the script

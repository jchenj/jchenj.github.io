---
layout: post
title: "Creating Bash Aliases"
date: 2020-06-08
---

Before today I'd heard about bash aliases, and how they allow one to create
 custom shortcuts for bash commands. Today I made my first alias and
  added it
  to my ~./bash_profile file so the alias will persist across bash sessions. 
  
1. Open file in text editor:
`vi ~/.bash_profile`


2. Press `i` to enter 'insert' mode 


3. Add new alias 
`# Create & activate venv, upgrade pip & setuptools
alias venv="python3 -m venv .env --copies && . .env/bin/activate && pip install --upgrade pip setuptools > /dev/null"`


4. Press ':wq' to save & quit ~/.bash_profile


5. Check file content to make sure changes saved correctly
`cat ~/.bash_profile`


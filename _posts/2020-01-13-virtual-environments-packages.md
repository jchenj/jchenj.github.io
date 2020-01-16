---
layout: post
title: Virtual Environments & Packages
date: 2020-01-13
---

Notes from Chapter 12 of the Python 3 official tutorial, [Virtual Environments & Packages](https://docs.python.org/3.7/tutorial/venv.html). 

### What?
* A virtual environment is a self-contained directory tree that contains an installation of a particular version of Python, plus additional packages. 
* `venv` is the module used to create & maintain virtual environments. It is included in the standard library for Python 3.3+.
* Command in terminal to create new venv is `python3 -m venv \[new directory name]`.' Here `python3 -m` means run the venv module as a script. The new venv is created with the default version of python3. 
* Need to activate the venv before using it. For MacOS, the command is `source \[directory-name]/bin/activate`.
* Command to deactivate venv is `deactivate`. 
* Use `pip` to install desired packages into `venv`. 
* (To list all packages in current venv, command is `pip list`.)
* (To see more info about a package, command is `pip show`.)
* Use `pip freeze` command in creating requirements.txt file.
* To install all requirements for an application, use the app's requirements.txt file and and run `pip install -r requirements.txt`

### So what? 
* Venvs are important for giving each project its own space where it can have all its dependencies (in appropriate versions), without running into potential conflicts among projects. 
* The most important tools for working with venvs are is the `venv` module (for creating them) and `pip` for adding additional packages, etc.  

### Now what?
* I'll want to learn how to set up venvs with new projects on PyCharm. 

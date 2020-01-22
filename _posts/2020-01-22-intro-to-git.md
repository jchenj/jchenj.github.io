---
layout: posts
title: Intro to Git
date: 2020-01-22
---
Resources:
Git tutorial
[Git Tutorial for Beginners: Command-Line Fundamentals](https://www.youtube.com/watch?v=HVsySz-h9r4) 

###Previous experience
Have git hub account
* Cloned a repo to my laptop
* Navigating within github repos

###Today I did:
* Updated command line tools after Catalina update so I could use git in terminal

Learned:
* Running git version 2.21 (Apple Git-122.3) Found this with `git --version`
* Setting global config variable:

## Local:
* Practice with:
`git commit <branch-name>`
**Create branch**
`git branch <branch-name>`
**Force move of branch**
`git branch -f <name-of-branch-to-move> <target-location>

`git checkout <branch-name>`
Create a new branch & checkout in one command:
`git checkout -b <branch-name>`
Moving HEAD to commit:
`git checkout <commit-name>`

`git merge <branch-name>`
`git rebase <branch-name>`
* Relative refs with `^` and `~`
* Reassigning a branch to a commit

Reversing changes in git
`git reset <new-location-of-branch-reference>` -- this works for local machines only, not remote branches that others are using
`git revert <location-of-changes-to-delete>` -- creates a new commit that undoes changes of previous commit

##Remote
`git clone` - make local copies of remote repository
`git fetch` - get data from a remote repository - does not change local files. Seems to update all data, regardless of branch.
* There's a command that combines `git fetch` and `git merge` -- `git pull`
* `git pull` - seems to work on all branches
* `git push` - uploads your changes to a specified remote ('publishing your work'). `git push` will fail if the remote has been updated
while you're still working on the old version. In this case `git fetch`, `git rebase o/master`, then `git push`
* Or you can do `git fetch`, `git merge o/master`, `git push`
* `git pull --rebase`is shorthand for `git fetch`, `git rebase`

* Merging feature branch work onto `master`
* Pulling & pushing from remote

* `git pull --rebase`is shorthand for `git fetch`, `git rebase`
* `git pull --rebase`is shorthand for `git fetch`, `git rebase`

## Initialize respository from existing code 
* Run `git init` from terminal while in directory containing project 
* `rm -rf .git` - removes `.git` directory recursively & forcefully (without confirmation)
* `git status` - get status of current directory
* `touch .gitignore` - creates .gitignore file, a text file with files we want git to ignore (can use wildcards)
* `git add -A` - add all untracked/changed files to staging area
* `git add <filename>` - adds individual file to staging area 
* `git reset` - removes all files from staging area
* `git commit -m "<message>"` - commits file(s) in staging area with message
* `git log` - see the commit just made 

## Cloning a remote repository
* `git clone <remote-repo-url> <target-location>` - clones a remote repo to target directory
* `git reset <filename>` - removes file from staging area

## Viewing info about remote repo
* `git remote -v` - lists info about remote repo
* `git branch -a` - lists all branches (locally & remotely)

## Pushing changes to remote branch
* `git diff` - show the changes made locally
* Then `git status` to check which files have changes to be committed
* `git add -A` - add all changed files to staging directory
* `git commit -m "<message>"` - commit files in staging directory
* First `git pull` (pulls any changes since version we have locally), then `git push origin master` - (`origin` is name of remote repo and `master` is branch to push to)

## Merge a branch
* `git checkout master`
* `git pull origin master`
* `git branch --merged` - shows which branches have already been merged
* `git merge <branch-name>`
* `git push origin master`

## Deleting a branch 
* Use once branch already merged
* `git branch -d <branch-name>` - deletes branch locally
* `git push origin --delete <branch-name>` - deletes branch from remote repository

## Create a feature branch
* `git branch <branch-name>` - creates new branch
* `git branch` - lists all branches
* `git checkout <branch-name>` - start working on specified branch

## Push branch to remote repo
* `git push -u origin <branch-name>` - push branch to remote repo. (`-u` flag indicates that local branch & remote branch are assosciated - will need to look into details for this)

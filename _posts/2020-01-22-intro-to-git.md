---
layout: posts
title: Intro to Git
date: 2020-01-22
---

Today I took my deepest dive yet into Git and by the end of the day achieved a bunch of firsts working from the command line, including initializing a repo from existing code on my local machine and cloning a remote repo. 

The main resources I used were:
* [Learn Git Branching](https://learngitbranching.js.org/Git tutorial) - nice interactive exercises, great to see visual representations of the current & goal states of the branches. 
* [Git Tutorial for Beginners: Command-Line Fundamentals](https://www.youtube.com/watch?v=HVsySz-h9r4) - packs a lot into half-hour video, very clear explanations & shows all steps in the terminal

I should say that before even getting started I ran into an issue, as attempting to run Git resulted in an error like `xcrun: error: invalid active developer path (/Library/Developer/CommandLineTools), missing xcrun at /Library/Developer/CommandLineTools/usr/bin/xcrun`. 

It turned out that this problem was related to my recent update to macOS Catalina, and I needed to update Xcode Command-line Tools with `xcode-select --install`. The Stack Overflow post I found describing the problem and solution(s) is [here](https://stackoverflow.com/questions/52522565/git-is-not-working-after-macos-update-xcrun-error-invalid-active-developer-pa).(I may need to consult this in the future, as it sounds like this issue pops up after every macOS update.)

Anyway, back to the main event. Prior to today I'd had seen a demo of Git from the command line and listened to one podcast about it, but hadn't used it myself. I had set up a Git Hub account, set up, forked and modified repos using the web interface. 

## Key achievements of the day
* Set up global config variables for Git
* Cloned the repo for the [TalkPython PyCharm course](https://training.talkpython.fm/courses/details/mastering-pycharm-ide) so I can stay updated with changes made by the instrutor. 
* Set up a new repo on Git Hub with files from my photo album project, cloned it on my local machine & invited a collaborator. 

## Next steps
* Update Git (I ran `git --version` and saw that I'm running version 2.21 (Apple Git-122.3). The most recent version is 2.23.0
* Continue learning Git fundamentals & using them in my projects 

## Notes from today
### Working locally
**Create branch**
* `git branch <branch-name>`
**Commit to branch**
* `git commit <branch-name>` 
**Force branch move**
* `git branch -f <name-of-branch-to-move> <target-location>
**Start working on branch**
* `git checkout <branch-name>`
**Create a new branch & checkout in one command**
* `git checkout -b <branch-name>`
**Move HEAD to specified commit**
* `git checkout <commit-name>`
**Merge**
* `git merge <branch-name>`
**Rebase**
* `git rebase <branch-name>`
**Relative refs**
* Use `^` (one commit up) and `~N` (N commits up)
**Reversing changes**
* `git reset <new-location-of-branch-reference>` - works for local machines only, not remote branches that others are using
* `git revert <location-of-changes-to-delete>` - creates a new commit that undoes changes of previous commit

**Initialize respository from existing code**
* Run `git init` from terminal while in directory containing project 
* `rm -rf .git` - removes `.git` directory recursively & forcefully (without confirmation)
* `git status` - get status of current directory
* `touch .gitignore` - creates .gitignore file, a text file with files we want git to ignore (can use wildcards)
* `git add -A` - add all untracked/changed files to staging area
* `git add <filename>` - adds individual file to staging area 
* `git reset` - removes all files from staging area
* `git commit -m "<message>"` - commits file(s) in staging area with message
* `git log` - see the commit just made 

### Working on remote repo
**Clone a repo locally**
* `git clone <remote-repo-url> <target-location>` - clones a remote repo to target directory
* `git reset <filename>` - removes file from staging area
**Viewing info about remote repo**
* `git remote -v` - lists info about remote repo
* `git branch -a` - lists all branches (locally & remotely)
**Get changes from a remote repository**
* `git fetch` 
* Does not change local files. Seems to update all data, regardless of branch.
**Fetch & merge in one command**
* `git pull`
* Seems to work on all branches
**Upload changes to remote**
* `git push`
* Will fail if the remote has been updated since version you have locally
* In this case `git fetch`, `git rebase o/master`, then `git push`
* Or you can do `git fetch`, `git merge o/master`, `git push`
* `git pull --rebase`is shorthand for `git fetch`, `git rebase`

**Pushing changes to remote branch - workflow**
* `git diff` - show the changes made locally
* Then `git status` to check which files have changes to be committed
* `git add -A` - add all changed files to staging directory
* `git commit -m "<message>"` - commit files in staging directory
* First `git pull` (pulls any changes since version we have locally), then `git push origin master` - (`origin` is name of remote repo and `master` is branch to push to)

**Merge a branch**
* `git checkout master`
* `git pull origin master`
* `git branch --merged` - shows which branches have already been merged
* `git merge <branch-name>`
* `git push origin master`

**Deleting a branch**
* Use once branch already merged
* `git branch -d <branch-name>` - deletes branch locally
* `git push origin --delete <branch-name>` - deletes branch from remote repository

**Create a feature branch**
* `git branch <branch-name>` - creates new branch
* `git branch` - lists all branches
* `git checkout <branch-name>` - start working on specified branch

**Push branch to remote repo**
* `git push -u origin <branch-name>` - push branch to remote repo. (`-u` flag indicates that local branch & remote branch are assosciated - will need to look into details for this)

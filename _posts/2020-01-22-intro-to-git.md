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


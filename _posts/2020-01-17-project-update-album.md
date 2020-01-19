---
layout: post
title: Project update: Photo album, Jan. 17
date: 2020-01-17
---

Today I picked up working on a photo album site I started late last year. Leading up to today I'd written two Python scripts for the project - one to create an HTML page for each image, and the other to create an index page with a link to each image's page. 

My goals for today were 1) to improve the index page by replacing the text link with a thumbnail image link and 2) to add a link from each image page back to the index. 

**Successes**
* I achieved both goals, albeit with some caveats (see below).
* I got to use some of my new bash skills! I used `cat` to see the contents of one of my files that wasn't opening for some reason in IDLE, and used output redirection to create a copy of this file. 
* I achieved some HTML 'firsts', namely making image links & link buttons. 
* Today's work session was a good reminder of the amount of time & effort it takes to get reoriented with a project I haven't worked on it for a while - even when I've written all of it myself!

**Challenges**
* While I successfully resized the images to thumbnail size, the resizing sets the image width to 100, regardless of whether it's oriented horizontally or vertically. So overall the image resizing factor is uneven - the vertically-oriented images are proportionally larger than the horizontal ones. I'll need to learn how to do resizing that takes orientation into account. 
* I worked for several hours to make this amount of modest progress. The number of false starts and overall length of time did cause me to feel a bit discouraged about how long it seems it will take to learn to make an "modern" website. 

**Next steps**
* Following a code review I've got a number of to-dos to improve these two scripts - more on that next time. 
* Today's work session made me wonder about best practices for where/how to store related files for a project (e.g. all in one directory? In different subdirectories?) I found an [article on dealing with files](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/Dealing_with_files) on mozilla.org - I'll read through that & apply what I learn to the file structure for this & future projects.
* I'll be adding my code to a GitHub repository & start using version control on it. 

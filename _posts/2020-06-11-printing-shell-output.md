---
layout: post
title: "Printing shell output""
date: 2020-06-11
---

For the past two weeks I've been working on my most extensive [open source
 issue](https://github.com/beeware/beeware/issues/53) to date, which came out
  of an error I got as I was going through the [BeeWare project](https
  ://beeware.org/) [tutorial](https://docs.beeware.org/en/latest/index.html
  ). 
  
  I've learned a lot from the experience so far, and planning to write a post
   eventually summarizing some of the key takeways. For the moment,just
    documenting to handy bash commands I've learned in the process & found
     helpful for saving script output a file and later comparing the
      differences across two files:
      
### `tee`
Reads from standard input, writes to standard output and file

Example from my project:
```
jchen@ribka:~/Desktop/FOSS/beeware/briefcase2/briefcase/src/macOS/Hello World/Hello World.app/Contents/MacOS$ ./Hello\ World | tee nv_direct.txt
```
Run scripts, display output on console and save to file nv_direct.txt

[man page for `tee`](https://ss64.com/bash/tee.html)

### `diff`
Display differences between two files

Example from my project:
```
(.env) jchen@ribka:~/Desktop/FOSS/beeware/briefcase2/briefcase/src/macOS/Hello World/Hello World.app/Contents/MacOS$ diff -y --suppress-common-lines no_nv_direct.txt nv_direct.txt | tee diff.txt
```
Compare two files & print different lines only side-by-side
[man page for `diff`](https://ss64.com/bash/diff.html)

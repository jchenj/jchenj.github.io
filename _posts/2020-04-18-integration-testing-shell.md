---
layout: post
title: "First steps to integration testing using shell scripts"
date: 2020-04-17
---

First steps to integration testing. Now that quite extensive unit tests

Write shell script

Did bash tutorial - only single lines in Bash. 

Wrote scripts for python

Way to test code out as if user did.

So for only for unencryed because encrypted needs password. Might be able to do this by having passwords in a separate file and read them in as needed using a pipe`

Important to remove the test file at end of each test sequence. 

````
#!/bin/bash

echo "Running tests..."

python3 passman.py -f testfile -nf
python3 passman.py -f testfile -na bob
python3 passman.py -f testfile -cp bob

rm testfile

echo "Done running tests"

````

How to run shell script:
need to make it runnable: `chmod +x <filename>`

Then have three options:
````bash <filename
./script-name-here.sh
OR
sh script-name-here.sh
OR
bash script-name-here.sh
````
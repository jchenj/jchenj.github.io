---
layout: post
title: "Deciphering KeyError when using csv.DictReader()"
date: 2020-02-12
---

While I've been blogging less recently, it's been busy & productive times. I finished the TalkPython course *Mastering PyCharm* and have been putting my new PyCharm powers to work on a couple of new personal projects - a command-line password manager and a Flask web app - while also diving into a course on web development using Python. 

I've found that using Evernote for learning notes seems be better for my workflow than blogging, so I'll stick to using the blog for documenting wins of any size and aha moments - and I had a good one come up today during work on the password manager! 

To start out with, I just wanted to read in data from a CSV file and print it out. Given my previous experience with the `csv` module in *Automate the Boring Stuff*, I wasn't anticipating any major difficulties with this and in short order came up with: 

```
import csv
def password_manager():
    datafile = 'test-spreadsheet.csv'
    account_header = 'Account-name'
    password_header = 'Password'

    # Read in data from spreadsheet
    with open(datafile) as csvfile:
        reader = csv.DictReader(csvfile)
        for row in reader:
            print(row[account_header], row[password_header])
```

When I ran it, though, I ran into a snag. While the program had no difficulty printing `row[password_header]`, I got a KeyError for `account_header`. I double-checked and confirmed that when viewed in Excel the header for Column A did appear as 'Account-name', just as I'd entered in the program. Keeping the frustration level (mostly) in check, I came up with several ideas on the source of the problem. For example, I wondered if the bold formatting of the header line could be the culprit. (Though this wouldn't explain why the second column's header posed no problems.) I also was vauguely aware that there could be some formatting at work on the first cell, invisible in Excel but picked up by the csv module, but I didn't know how explore this. So off to Stack Overflow I went!

In the end, a couple of searches for 'KeyError csv' got me to the correct explanation and solution, [here](https://stackoverflow.com/questions/12534110/keyerror-when-using-dictreader) and [here](https://stackoverflow.com/questions/17912307/u-ufeff-in-python-string#17912811). Indeed, there was a bit of Excel-invisible formatting at work. 

To take a look at the first row, as parsed by Python, I ran:
```
with open(datafile) as csvfile:
    reader = csv.DictReader(csvfile)
    row1 = next(reader)
    print(row1)
```  
The output showed me the unexpected formatting in Cell A1:
```
OrderedDict([('\ufeffAccount-name', 'frog'), ('Password', 'green')])
```
I learmed that the '\ufeff' before the first header value was the [byte order mark (BOM)](https://en.wikipedia.org/wiki/Byte_order_mark), which can be removed from the read result by entering the correct encoding in the function parameters. When I revised the first line as below, the function ran as expected:
 
 ```
 with open(datafile, encoding='utf-8-sig') as csvfile:
...
```

A little bit of hair-pulling, but in the end some interesting learning, and good follow-up to the [BaseCS episode on encoding](https://www.codenewbie.org/basecs/4) I listened to a while ago. Onwards! 
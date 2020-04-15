---
layout: post
title: "Splitting and joining in Python"
date: 2020-04-15
---

### From list of lists to string with `.join()`
Needed to go from a list of lists to a string
List of lists looks like ---. To do with a for loop, start with an empty string. First join all elements in one row. Add each row to the string, followed by a new line. 
 
````
dataStr = ''
for elem in data:
        row = (','.join(elem))
        dataStr = dataStr + row + '\n'
````
Alternatively, I saw how to do this with a list comprehension: 
```
dataStr = '\n'.join(','.join(row) for row in data)
```
While I read that the list comprehension way is more pythonic, I'm thinking it's good for me to use the for loops to understand the structure first. Also, I find them more straightforward to read & understand. 

### From from string to list of lists with `str.split()`

Also needed to go from string to list of lists
String is output of `decryptFile()` and looks like ----. Need to create a sublist each time there is a newline. Then all items within that row are elements in the sublist. To do this with a for loop, make an empty list first, create rows and then iterate through the elements in each how, adding them to the sublists. 

````
data = []
rows = contents.split('\n')
for r in rows:
    data.append(r.split(','))
````
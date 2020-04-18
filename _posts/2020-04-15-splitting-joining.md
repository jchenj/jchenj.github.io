---
layout: post
title: "Splitting and joining in Python"
date: 2020-04-15
--- 

I got some good experience manipulating strings in Python today using `.split()` and `().join` in the context of continuing to work on the my password manager program. Specifically, I was working on the functions for encryption and decryption and needed to transform the data from string format (the encrypted form) into lists of lists (the unencrypted form), and back again.  

### From list of lists to string with `.join()`
    
In unencrypted form, the data in a file is contained as a list of lists:

`[['Account-name', 'Password'], [bird', 'ovmejunj'], ['fish', 'cmyehkzz']`

I need to put this data into a string in which the there is a comma between the members of each sublist and a newline between each sublist. I start with an empty string. Then I iterate through each element (sublist) in the data using a for loop. First I create rows by joining each element in a sublist with a comma. Then I add each row to the string with a newline between each row. 
  
````
dataStr = ''
for elem in data:
        row = (','.join(elem))
        dataStr = dataStr + row + '\n'
````

It is also possible to accomplish this in a single line:

```
dataStr = '\n'.join(','.join(row) for row in data)
```

While the first option is longer and might be less pythonic, I find it easier to read and understand, so my preference for the moment is to use for the for loop method. 

### From from string to list of lists with `.split()`

The output of `decryptFile()` is a single string containing all file data. For example, the decryped data for a file containing accounts looks like:

`'Account-name,Password\nbird,eozajvdz\nfish,nohsbmwc\ndog,uwocotaj'`

I need to split the string into a list at each newline, and separate each element within this (sub)list with a comma. To do this, first I create an empty list - this will be the outer list. Then I create rows by splitting the decrypted file contents at the newline. Finally, I separate each element in the rows with a comma and then add it to the data list. 

````
contents = decrypt_file(self.fname, self.password)
data = []
rows = contents.split('\n')
for r in rows:
    data.append(r.split(','))
````
---
layout: post
title: "Gotcha with list.append()"
date: 2020-04-12
---

Today I continued working on my command line password manager program, implementing a couple of private methods for reading and writing files and refactoring the API methods to use these new methods. This is a step along the path to adding encryption functionality to the program. As I was refactoring the last API method, I ran into a quick gotcha related to list mutability in Python. 

The API function, `create_new_account()` adds an account name and password to the password file, provided that the account doesn't already exist. I had written the function to the point where all there was left to do was append (in memory) the new data to the existing file data and then write the data to the file. 

````
def create_new_account(self, alphabet, password_length):
    assert (password_length > 0)
    if self.check_if_account_exists():
        raise RuntimeError("Account '{}' already exists".format(self.acname))
    new_pass = create_password(alphabet, password_length)
    data = self._readFile()
    fields = [self.acname, new_pass]
````

The final couple of lines of code seemed straightforward to me - one to append `fields` to `data`, one to write the data to the file and a final `return`:
 
```
new_data = data.append(fields)
self._writeFile(new_data)
return
````

I added this, tested it and was got an error: `TypeError: 'NoneType' object is not iterable`. How could it be that `new_data` was `NoneType` when I knew `_readFile()` works, I'd confirmed the contents of `fields` and I knew how `list.append()` works? 

The answer was I was missing a key piece of info about `list.append()`, namely that it changes the list in place and returns `None` (rather than the changed list). I was familiar with the concept of mutable types in Python, and knew that lists were one such type - but I didn't realize the implications this had for list methods like `list.append()`. 

With this new info in mind, I changed the final lines of code:

````
data.append(fields)
self._writeFile(data)
return
````

And with that my refactoring is done and I'm ready to move ahead adding functions to deal with encrypted files to each API method. In the meantime, one key takeaways from today's gotcha: 

While I'm familiar with many of the fundamentals of Python, it takes a lot of experience to understand the implications they have for writing and debugging code. In addition to learning on my own with docs, Stack Overflow, etc. talking over issues with experienced folks is a great way to navigate these issues. Plus, it's validating to hear that everyone goes through this learning process - and that it repeats to some extent with each new programming language that one learns!
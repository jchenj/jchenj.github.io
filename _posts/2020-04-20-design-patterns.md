---
layout: post
title: "Design patterns"
date: 2020-04-20
---

While I'd heard about design patterns before today, today was the first time I used one in refactoring my code. 

I was working on enhancing the `change_password` function in the password manager program I'm working on. The original version of the function only allowed one to change the password to one randomly generated password. We wanted the user to have the option to set the password. 

### Original version
```python
def change_password(self, alphabet, password_length):
    """
    Changes password of specified file to a new password of specified length from ALPHABET
    Assumes account name exists in file
    Assumes password length is integer > 0
    :param alphabet: string of full alphabet
    :param password_length: length of password
    :return: None
    side effect: file with new password for specified account
    """
    if not self.check_if_account_exists():
        raise RuntimeError("Account '{}' does not exist".format(self.acname))
    new_password = create_password(alphabet, password_length)
    # read in the password file
    data = self._readFile()
    for row in data:
        if row[0].strip() == self.acname:
            row[1] = new_password
    self._writeFile(data)
    return
```

As I started working on this, my initial approach was to add some additional conditions to the the `change_password` function. I would add a `password` parameter to the function. If this parameter set, then the password to that. Otherwise, if the `alphabet` and `password_length` parameters were set, then the program would generate and set a random password. While it felt unwieldy to work with these three parameters, I didn't have a better idea initially. 

On talking the problem over, I learned that there was a cleaner way to do this. I could separate the creation of the new password (whether specified or random) from updating the file with the new password. I pulled out the creation of the new password into two new functions, `set_pw` for specified passwords and `set_pw_rand` for random passwords. The purpose of `change_pw` changed to only include updating the file with the passwords created by the other two functions.

At the end of the day, the three functions I wrote were:

### New version 
```python

def set_pw_rand(self, alphabet, password_length):
    """
    Sets password of account to a new random password of specified length from ALPHABET
    Assumes password length is integer > 0
    :param alphabet: string of full alphabet
    :param password_length: length of password
    :return new_password: string
    """
    new_password = create_password(alphabet, password_length)
    self._change_password(new_password)

def set_pw(self, specified_pass):
    """
    Sets password of specified account to a new specified password
    Assumes account names exists in file
    :param specified_pass: specified new password (string)
    :return: new_password: string
    """
    self._change_password(specified_pass)

def _change_password(self, new_password):
    """
    Changes password of specified account to new (pre-set) password
    Assumes account name exists in file
    :param new_password: new password (string)
    :return: None
    :side effect: file with account updated with new password
    """
    if not self.check_if_account_exists():
        raise RuntimeError("Account '{}' does not exist".format(self.acname))
    # read in the password file
    data = self._readFile()
    for row in data:
        if row[0].strip() == self.acname:
            row[1] = new_password
    self._writeFile(data)
    return
```

I liked how splitting up the two tasks done by the original function made the new, enhanced version much easier to work with. I'm looking forward to learning more about design patterns and how to apply them in my code. 
 
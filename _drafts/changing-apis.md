---
layout: post
title: "Changing APIs with minimal change to codebase"
date: 2020-05-27
---

Wanted to change API so encryption was default. 

Changed the command line args - deleted -e --encryptd and added -no-encrypt. 

Then I needed to change how this arg was interpreted in the create_new_file function, which takes a Boolean `encrypt` parameter. Changing the function itself would have meant changing everything that calls the function - many tests, and other function. Instead, I changed how the -no-encrypt arg was interpreted in create-new-file, by negating it (`not no-encrypt). This was trippy to me - I'd never seen that you could negate in a func signature! 

Overall I loved how this change limited the amount I needed to change in the codebase. I just needed to make sure to update my integration to use the new params correctly. 
---
layout: post
title: "Photo album update"
date: 2020-01-20
---

Over the last two days I've continued working on the photo album scripts and made some good progress...

**Successes**
* Changed the format of the index so that it's based on a table. This makes it so the photos are arranged in rows, rather than in one column vertically - much more user friendly! 
* I changed several hard-coded values in the HTML generator script to parameters, making the script easier to re-use
* I added code to allow both scripts to be run either as main or imported as a module, and by doing so better understood this process:
`if __name__ == "__main__":    # if the script is being run as the main code \\
  makeIndex('./photoSite', '.jpg')  # run the code with these values for the parameters`
* To run the code with other values for parameters, I ran Python in the terminal and imported the script:
`python3 #run Python \\
import makeIndex  # import name of script without '.py'
makeIndex.makeIndex('./other-photos', 'jpg') # call function with desired values as parameters`

**Challenges**
* When I was researching how to format the index using a table, I read that this is an outdated method of doing page layout, which folks are generally advised to avoid. While I generally like to use best practices in my work, in this case I stuck with the table, as it was good practice for me and got me the results I was looking for. I hope to learn better ways to format pages down the line! 

**Future work**
* I'd likr to better understand how to format docstrings to describe useage, parameters, etc. 

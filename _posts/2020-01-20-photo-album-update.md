---
layout: post
title: "Photo album update"
date: 2020-01-20
---

**Successes**
* Added file format as parameter
* Added code to allow script to be run as main or imported, and by doing so better understood this process:
`if __name__ == "__main__":    # if the script is eing run as the main code \\
  makeIndex('./photoSite', '.jpg')  # run the code with these values for the parameters`
* To run the code with other values for parameters, I ran Python in the terminal and imported the script:
`python3 #run Python \\
import makeIndex  # import name of script without '.py'
makeIndex.makeIndex('./other-photos', 'jpg') # call function with desired values as parameters

**Challenges**



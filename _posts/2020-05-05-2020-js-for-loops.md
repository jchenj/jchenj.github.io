---
layout: post
title: "For-loops in JavaScript"
date: 2020-05-05        
---

First taste of differences between JS and Python. 

Writing a func to sum numbers in a list. Learned that there are two kinds of for loops I could use here: 

for/in to loop over indexes (the properities of an element)
```javascript
for(let i in numbers){
      total += numbers[i];
    }
```
for/of to loop over the list elements (loop over iterables themselves) 
```javascript
for (let num of numbers){
      total += num
    }
```

Also learned about the for loop:
```javascript
  function range(start, end) {
    let elements = []
    for (let i = start; i <= end; i += 1){
      elements.push(i);
    }
    return elements
  }
```
[Explanation of all the types of iteration in JS](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#for...in_statement)


---
layout: post
title: Classes in Python
date: 2019-12-14
---

I've been working through the official Python tutorial (release 3.7.5) and today began [Chapter Nine, Classes](https://docs.python.org/3.7/tutorial/classes.html). Drawing on the ["Know-Want to Know-Learned" technique](https://en.wikipedia.org/wiki/KWL_table) from education, I'll summarize what I know about this topic and my current questions before working through the tutorial. 

**Know**
* My previous exposure to classes was toward the end of Nina Zacharenko's course on [Python Fundementals](https://frontendmasters.com/courses/python/) on Frontend Masters. (I took it during a free access offer, which was fantastic.) From that course, I think I recall that classes are related to object-oriented programming. Classes allow the programmer to create a type of object with certain attributes. For example, the class *Car* might have four wheels and a color, etc. The programmer can then create as many instances of a class as needed without repeating the process of describing the properties of each instance. For example, one could create a yellow car and red car and these will both have four wheels by virtue of being members of the class *Car*.  
* A programmer can also make subclasses. For example, there might be a subclassof *Car* called *Sedan* that has four doors and another subclass called *Hatchback* that has two doors.
* The advantage of classes is that it allows programmers to avoid duplicating code by writing a class once and building on it for additional needs.<br>

**Want to know**
* I'd like to see how classes are used more practically in writing programs. I understand the car example conceptually, but I haven't seen it in use in actual code much yet.

**Learned**
* *What is `\__init__()?`* This is a special method. For a class that includes a `\__init__()` method, when the class is instantiated, `\__init__()` is immediately invoked for the new class instance. `\__init__()` always includes a `self` argument - i.e. `\__init__(self)` - but can include additional arguments if desired. 
* *Why should one not use mutable objects (e.g. lists and dictionaries) as class variables?* When values are added to mutable objects in class values, all values are shared with all instance variables, which may not be desired. To avoid this, instance variables should be used for mutable objects, so that each instance will only have the values assigned to it. 
* *What is `iter()?`* `iter()` is a function that returns an iterator object. It defines the method `\__next__()` which accesses the elements in the container one item at the time. When there are no more elements, `\__next__()` raises the `StopIteration` error. 
* *What is an iterator?* An iterator is an object that can be iterated on. In Python it is an object that implements the iterator protocol, which consists of the two methods `\__iter__()` and `\__next__()`. 
* *What are generators?* Generators are tools that create iterators. 

**For the future...** 
* Private variables - When are they used? What exactly is name mangling? 

---
layout: post
title: Classes in Python
date: 2019-12-14
---

Inspired by a talk on "Learning in Public" I heard at at meetup last week, I'm going to document my learning more on this blog 
rather than posting more "significant" problems solved. These posts are intended mostly as notes to myself on lessons learned. <br>

I've been working through the official Python tutorial (release 3.7.5) and today began Chapter Nine, Classes. Drawing on the KWL
technique from education, I'll summarize what I know about this topic before doing the tutorial and my current questions about the topic, 
then come back and describe what I learned at a high level once I've completed it. <br>

**Know**
* My previous exposure to classes was toward the end of Nina Zacharenko's course on Front End Masters. From that, I think I recall
that classes are related to object-oriented programming. Classes allow the programmer to create a type of object with certain
attributes. For example, the class *Car* might have four wheels. 
* A programmer can build new objects based on the class of car, and can also make subclasses. For example, there might be a subclass
of *Car* called *Sedan* that has four doors and another subclass called *Hatchback* that has two doors.
* The advantage of classes is that it allows programmers to avoid duplicating code by writing a class once and building on it for additional
needs.<br>

**Want to know** <br>
* I'd like to see how classes are used more practically in writing programs. I understand the car example conceptually, but it doesn't seem very useful at this point.<br>

**Learned** <br>
* *What is \__init__()?* This is a special method. For a class includes a \__init__() method, when the class is instantiated, \__init__() is immediately invoked for the new class instance. \__init__() always includes a *self* argument - i.e. \__init__(self) - but can include additional arguments if desired. 
* *Why should one not use mutable objects (e.g. lists and dictionaries) as class variables?* When values are added to mutable objects in class values, all values are shared with all instance variables, which may not be desired. To avoid this, instance variables should be used for mutable objects, so that each instance will only have the values assigned to it. 
* *What is iter()?* iter() is a function that returns an iterator object. It defines the method \__next__() which accesses the elements in the container one item at the time. When there are no more elements, \__next__() raises the StopIteration error. 
* *What is an iterator?* An iterator is an object that can be iterated on. In Python it is an object that implements the iterator protocol, which consists of the two methods \__iter__() and \__next__(). 
* *What are generators?* Generators are tools that create iterators. 


**For the future** <br>
* Private variables - When are they used? What exactly is name mangling? 

---
layout: post
title: Brief Tour of the Standard Library II
date: 2019-12-19
---

The second part of the tour of the Python standard library covers more advanced modules. As with Part I, I've organized my notes into two sections: one for those modules I've already worked with and the other for modules that were new to me. 

## New (to me) modules:
### `array`
* Provides an array object, which is like a list but stores only homogenous data and stores it more compactly.
* Python `int` objects are usually 16 bytes per entry
* For example, an array of numbers could be stored as two byte unsigned binary numbers (typecode 'H')

### `bisect`
* Functions for manipulating sorted lists

### `collections`
* A module with specialized container datatypes (alternatives to those containers built-in with Python).
* Example: `deque()` is a list-like object with faster appends & pops but slower lookups in the middle.

### `decimal`
* Support for decimal floating point arithmetic. Offers several advantages to float datatype.

### `gc`
* Provides an interface to the optional garbage collector

### `heapq`
* Functions for implementing heaps based on regular lists
* A heap is a specialized tree-based data structure where any node has a lower value than any of its children

### `locale`
* Accesses a library of locale-specific data formats
* Can set the locale and format string's according to the conventions of that locale

### `logging`
* Logging module can be used to customize logging message at various levels (e.g. `debug`, `info`, `critical`, etc.)
`
### `reprlib`
* `reprlib.repr(*obj*)` returns an abbreviated printable version of an object

### `string`
* The string module contains a `Template` class which users can use to customize applications without changing them.  

### `struct`
* The `struct` module is ued for working with binary data record formats

### `textwrap`
* Formats paragraphs of text to fit a given screen width

### `weakref`
* Provides tools for tracking objects without creating a reference

## Modules I've worked with previously:
### `pprint`
* Can specify max. width of printed result in second argument - `pprint.pprint(*object, max. width*)`

### `threading`
* The threading module can be used to run tasks in the background while the main code continues to run. Preferable to use the  queue module for coordination among threads rather than threading module. 

---
layout: post
title: Floating Point Arithmetic Issues & Limitations
date: 2020-01-14
---

Notes from Chap. 15 of the official Python tutorial

###Key terms
* Base 2 (binary system) - numbers are expressed using only two symbols, typically 0 and 1. 
* Base 2 fractions - fractions in one base (e.g. base 10) can be converted to another base (e.g. base 2) using several methods.
* Base 10 (decimal system) - numbers are represented with 10 symbols (e.g. arabic numerals) and a separator (e.g. a dot).
* Base 16 (hexadecimal system) - numbers are represented with 16 symbols, most commonly 0-9 for zero to nine and A-F for ten
to fifteen
* Bit - binary digit (e.g. 0 or 1)
* Floating point numbers - numbers with decimal points. (This is incomplete.)

###What?
* Floating point numbers are represented in computer hardware as base 2 (binary) fractions
* Representation error: Most decimal fractions can't be represented exactly as binary (base 2) fractions

###So what? 
* Python (and other programming languages) often won't display the exact decimal number one expects

###Now what?
* Use the `fractions` and `decimal` modules to make calcuations between floats, fractions & decimals 
* The `round()` function can be useful for post-calculation rounding so that inexact values become comparable
* Look at SciPy if doing a lot of floating point operations
* There are tools that can be used to get the exact value of a float (`float.as_integer_ratio()`, `float.from_hex()`, `math.fsum()`

---
title: Binary_Calculator_-_Multiplication
description: 
published: true
date: 2025-10-12T23:32:55.479Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:32:51.586Z
---

## **Description**

*[Back to Binary Calculator - Main Page](Binary_Calculator "wikilink")*

This circuit is more complicated than subtractor and adder. Binary
multiplier (as you can guess from its name) can multiply two binary
numbers.

You can have some problems when you will try to build and use a
multiplier -

1.  Unlike adder and subtractor (whitch have full and half version),
    this circuit has only half version (although it's not called half
    here). That means you can't connect the same circuits in series to
    make the final circuit have more bits. If you want to make this
    circuit have more bits, you'll have to completely rebuild it.
2.  Multipliers are using binary code, so it can be confusing to work
    with them. Binary code uses just 0 and 1, so you can write a number
    in binary using just switches (ON=1, OFF=0).
3.  Binary code uses bits (you can image a bit as a place reserved for 0
    or 1).

If you want to build up one for yourself, you can look at this scheme of
**2 bits times 2 bits** multiplier -
![Binarymultiplier.jpg](Binarymultiplier.jpg "Binarymultiplier.jpg")

**A0** and **A1** stand for input of first factor - 2 bits, **B0** and
**B1** stand for input of second factor - 2 bits, **C0-C4** stand for
output - 4 bits

Or you can download this world file and test it yourself - [Binary
Calculator world
file](https://dl.dropboxusercontent.com/s/pdxfcvu4v9qg3r6/BinOperations.scworld?token_hash=AAHgWWkpA5AxzT1v35tiAHHUkqH_tQ9wAYLanSkx6xGqog&dl=1)

## **Tutorial for our world**

The multiplier is on the left side and it's labeled, so it won't be
problem to find it.

If you want to use it, don't forget these things -

1.  The multiplier has two groups of switches. The first group (left
    from X) represents first factor and the second group (right from X)
    represents second factor. Like on this picture -
    ![Multiplication.jpg](Multiplication.jpg "Multiplication.jpg")
2.  Our multiplier has just 2x2 bits, so these are all combinations of
    numbers you can count - 1x1,1x2,1x3,2x2,2x3,3x3
3.  It multiplies in real time, so please don't let the diodes interrupt
    you. You should look at them after finishing writing the numbers.

Binary_multiplier001.jpg Binary_multiplier002.jpg

*[Back to Binary Calculator - Main Page](Binary_Calculator "wikilink")*

[Category:Electricity](Category:Electricity "wikilink")
[Category:Circuits](Category:Circuits "wikilink")
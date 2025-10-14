---
title: Binary_Calculator_-_Subtraction
description: 
published: true
date: 2025-10-12T23:33:01.074Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:32:57.162Z
---

## **Description**

*[Back to Binary Calculator - Main Page](Binary_Calculator "wikilink")*

This circuit is another must-have for all calculators. Binary subtractor
(as you can guess from its name) can subtract two binary numbers.

You can have some problems when you will try to build and use a
subtractor -

1.  There are two types of subtractors - half and full. Both can
    subtract just two numbers (0,1), but full subtractor (unlike the
    half) can be connected to another full subtractor, whitch can
    operate with the 1st subtractor's output. That means you can
    subtract more numbers when you have more full subtractors. Each new
    subtractor will add you one bit (read bellow)
2.  Subtractors (doesn't matter if half or full) are using binary code,
    so it can be confusing to work with them. Binary code uses just 0
    and 1, so you can write a number in binary using just switches
    (ON=1, OFF=0).
3.  Binary code uses bits (you can image a bit as a place reserved for 0
    or 1). Each connected full subtractor will add one more bit. The
    numbers you can subtract are limited by the number of bits.

If you want to build up one for yourself, you can look at this scheme -
![Binarysubtractor.jpg](Binarysubtractor.jpg "Binarysubtractor.jpg")

**A** stands for minuend input, **B** stands for subtrahend input,
**BORin** and **BORout** stand for connecting with previous/next full
subtractor, **D** stands for output

Or you can download this world file and test it yourself - [Binary
Calculator world
file](https://dl.dropboxusercontent.com/s/pdxfcvu4v9qg3r6/BinOperations.scworld?token_hash=AAHgWWkpA5AxzT1v35tiAHHUkqH_tQ9wAYLanSkx6xGqog&dl=1)

## **Tutorial for our world**

The subtractor is on the right side and it's labeled, so it won't be
problem to find it.

If you want to use it, don't forget these things -

1.  The subtractor has two lines of switches. The first line represents
    minuend and the second line represents subtrahend. Like on this
    picture - ![Subtraction002.jpg](Subtraction002.jpg
    "Subtraction002.jpg")
2.  Our subtractor has just 4 bits, so the max number you can get from
    it is 15 (15-0)
3.  It subtracts in real time, so please don't let the diodes interrupt
    you. You should look at them after finishing writing the numbers.

Binary_subtractor001.jpg Binary_subtractor002.jpg
Binary_subtractor003.jpg

*[Back to Binary Calculator - Main Page](Binary_Calculator "wikilink")*

[Category:Electricity](Category:Electricity "wikilink")
[Category:Circuits](Category:Circuits "wikilink")
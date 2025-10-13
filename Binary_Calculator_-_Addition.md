---
title: Binary_Calculator_-_Addition
description: 
published: true
date: 2025-10-12T23:32:38.911Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:32:34.955Z
---

## **Description**

*[Back to Binary Calculator - Main Page](Binary_Calculator "wikilink")*

This circuit is a must-have for all calculators. It's also probably the
simplest circuit (used in calculator to count). Binary adder (as you can
guess from its name) can sum two binary numbers.

You can have some problems when you will try to build and use an adder -

1.  There are two types of adders - half adder and full adder. Both can
    sum just two numbers (0,1), but full adder (unlike the half) can be
    connected to another full adder, which can operate with the 1st
    adder's output. That means you can sum more numbers when you have
    more full adders. Each new adder will add you one bit (read below)
2.  Adders (doesn't matter if half or full) are using binary code, so it
    can be confusing to work with them. Binary code uses just 0 and 1,
    so you can write a number in binary using just switches (ON=1,
    OFF=0).
3.  Binary code uses bits (you can image a bit as a place reserved for 0
    or 1). Each connected full adder will add one more bit. The numbers
    you can sum are limited by the number of bits.

If you want to build up one for yourself, you can look at this scheme -
![Binaryadder.jpg](Binaryadder.jpg "Binaryadder.jpg")

**A** stands for 1st addend input, **B** stands for 2nd addend input,
**Cin** and **Cout** stand for connecting with previous/next full adder,
**S** stands for output

Or you can download this world file and test it yourself - [Binary
Calculator world
file](https://dl.dropboxusercontent.com/s/pdxfcvu4v9qg3r6/BinOperations.scworld?token_hash=AAHgWWkpA5AxzT1v35tiAHHUkqH_tQ9wAYLanSkx6xGqog&dl=1)

## **Tutorial for our world**

The adder is on the left side and it's labeled, so it won't be problem
to find it.

If you want to use it, don't forget these things -

1.  The adder has two lines of switches. The first line represents first
    addend and the second line represents second addend. Like this -
    ![Addition.jpg](Addition.jpg "Addition.jpg")
2.  Our adder has just 5 "showing" bits, so the max number you can get
    from it is 30 (15+15)
3.  It sums in real time, so please don't let the diodes interrupt you.
    You should look at them after finishing writing the addends.

Binary_adder001.jpg Binary_adder002.jpg Binary_adder003.jpg

*[Back to Binary Calculator - Main Page](Binary_Calculator "wikilink")*

[Category:Circuits](Category:Circuits "wikilink")
[Category:Electricity](Category:Electricity "wikilink")
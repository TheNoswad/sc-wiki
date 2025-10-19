---
title: Comparison_Circuit
description: 
published: true
date: 2025-10-12T23:39:40.053Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:39:36.115Z
---

This article describes a circuit that will compare two values and tell
you if one is LESS than, EQUAL to or GREATER than the other. It can be
used in a computer design or on its own. For instance it can measure a
weight and tell if the weight is more than a specified minimum.

The schematic is very simple as it has only one [Memory
Bank](../Recipaedia/Electrics/Memory_Bank.md "wikilink") at its heart (P).

<div style="overflow:hidden">

![Compare_2-Ops.jpg](Compare_2-Ops.jpg "Compare_2-Ops.jpg")

</div>

The actual compare bank is on the left (P). It outputs a different
number depending on whether Input-A is LESS, EQUAL or GREATER than
Input-B. What number is output depends on the application. In most
cases, it will be easiest to assign a different output BIT according to
each case. For example, bit-0 could be set when LESS, bit-1 set when
EQUAL or bit-2 set when GREATER.

This type of output is effectively a 'result flag' register as used in
computer architectures. It could be OR'd with other result flags and
stored in a holding register to be read out when needed.

The bank on the right (F) may be used to 'separate' the flag bits
according to what comparisons are wanted. It may be programmed to read
the bits and only respond to one single condition. That condition would
be decided by the SELECT input. Essentially this would ignore all bits
except the one wanted. That bit is then turned into a digital output
signal, a '0' bit would become a '0'hex and a '1' bit would become a
'F'hex.

Adding the function bank also gives the opportunity to use multiple bits
in the result. This way a GREATER OR EQUAL function may be achieved, for
example.

In a computer design, you would typically want to have a buffer between
the function bank's output and the data bus. The FLAGS output would
typically be OR'd with other result flags and accessed via another
register, latch or bus-enabling device.

[Category:Electricity](Category:Electricity "wikilink")
[Category:Circuits](Category:Circuits "wikilink")
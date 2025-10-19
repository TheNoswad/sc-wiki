---
title: Memory_Arrays
description: 
published: true
date: 2025-10-13T00:02:22.112Z
tags: 
editor: markdown
dateCreated: 2025-10-13T00:02:18.108Z
---

__NOTOC__ __NOEDITSECTION__ The [Memory
Bank](../Recipaedia/Electrics/Memory_Bank.md "wikilink") provides a convenient place for the
storage of data, as well as the possibility of many other functions.

This article (still under construction) discusses using multiple memory
banks to store larger amounts of data. This is most commonly needed in
computer circuits.

## Introduction

There are two basic types of memory; Read/Write Memory and Read Only
Memory. These are usually abbreviated with RAM and ROM, even though
'RAM' actually means Random Access Memory and does not necessarily
indicate the memory is writable. To avoid confusion, I will stick with
the common parlance as above.

Building ROM is simpler that RAM because you don't need to access the
write signal (through the rear of the chip). This article will start
with detailing ROM circuits.

## ROMs

A ROM stores data for later recall but this data must be placed in the
ROM "by hand". That means either by the character in-game or through
editing the xml file. That process is not discussed in this article.

### Smallest ROM

One memory 'cell' or a single Bank (8 bits or 256 locations):

<div style="overflow:hidden">

![Mem_Array_cells.jpg](Mem_Array_cells.jpg "Mem_Array_cells.jpg")

</div>

A typical row of cells (12 bits or 4,096 locations):

<div style="overflow:hidden">

![Mem_Array_rows.jpg](Mem_Array_rows.jpg "Mem_Array_rows.jpg")

</div>

[This link](https://app.box.com/s/u5cmmtcru36dul5mcehkn6ody1p33j7k) is a
simpler, 12 bit address array and is the basis for the full array. Since
SC 'analog' signals are 4 bits each, the 12 bit array can accept 3
analog inputs.

<div style="overflow:hidden">

![Array_12b.jpg](Array_12b.jpg "Array_12b.jpg")

</div>

To make the full 16 bit array, I simply duplicated this design 15 more
times.

[Here](https://app.box.com/s/j8b1zglw6hq007vn6imdc1htk3prfimk) is the
full array. This is a 64K-byte ROM and uses over 1,000 memory banks.
Only 512 of these hold the data and the rest are for interfacing with
the rest of the circuit and serve other functions. Even so, it would
indeed take a long time to program 512 banks by hand\!

Here's a picture of the 64K byte array:

<div style="overflow:hidden">

![64k_memory_bank.jpg](64k_memory_bank.jpg "64k_memory_bank.jpg")

</div>

## RAM or R/W memory

## Related Pages

[Memory Bank](../Recipaedia/Electrics/Memory_Bank.md "wikilink")

[Latch, Register Circuits](Latch,_Register_Circuits "wikilink")

[Using Analog Signals](Using_Analog_Signals "wikilink")

[RAM Circuits](RAM_Circuits "wikilink")

[Write Encoder](Write_Encoder "wikilink")

## Notes

The links above are to Box.net files. Box is more secure and more
respectful of my privacy than dropbox, so I prefer them. If you have
trouble getting the files, let me know and I'll copy them to droopbox...

[Category:Electricity](Category:Electricity "wikilink")
[Category:Circuits](Category:Circuits "wikilink")
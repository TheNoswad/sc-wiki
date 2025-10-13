---
title: Addition_Circuit
description: 
published: true
date: 2025-10-12T23:29:38.550Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:29:34.557Z
---

## Basic Adder

Here is a circuit for a 4-bit adder that uses only 2 [Memory
Banks](Memory_Bank "wikilink") . The picture shows the input and output
for the circuit as well. The I/O takes up much more space than the
circuit itself – the block on the right is the actual circuit. That’s
all it takes\!

<div style="overflow:hidden">

![4bit_adder.jpg](4bit_adder.jpg "4bit_adder.jpg")

</div>

The design is extremely simple. The two inputs go to the two banks in
parallel. One bank is programmed for the 4-bit output sum. The other
bank calculates the carry output bit. For a simple 4-bit core, that’s
all you need. For a larger word size, the higher order modules are more
complex to implement due to the carry, but they work on the same
principle. Also, your numerical representation can affect the circuit.
This circuit assumes unsigned/positive integers for simplicity.

You program the primary memory bank with:

0123456789ABCDEF123456789ABCDEF023456789ABCDEF013456789ABCDEF012456789ABCDEF012356789ABCDEF012346789ABCDEF012345789ABCDEF012345689ABCDEF012345679ABCDEF012345678ABCDEF0123456789BCDEF0123456789ACDEF0123456789ABDEF0123456789ABCEF0123456789ABCDF0123456789ABCDE

Compute the carry with:

0000000000000000000000000000000100000000000000110000000000000111000000000000111100000000000111110000000000111111000000000111111100000000111111110000000111111111000000111111111100000111111111110000111111111111000111111111111100111111111111110111111111111111

## Full Adder

That circuit works well enough if that's all you need. Usually an
addition requires more than 4 bits, however. That means we need to have
another, more complex circuit for higher 'nibbles' of data. (A nibble is
a 4-bit chunk of data, since a byte is 8-bits. LOL but seriously\!) This
circuit needs to have a carry IN, as well as a carry OUT.

The diagram below is for a full 8-bit addition module. At the top of the
picture is the basic adder, with its carry out. This works for the
lowest nibble of data since it needs no carry IN. The portion in the
dotted box is the FULL ADDER which includes a carry IN and the carry
OUT. You can extend this design for arbitrarily large data widths by
duplicating this portion and chaining the carry OUT from the module for
the lower data to the carry In of the next higher module.

<div style="overflow:hidden">

![Full_Adder_circuit.jpeg](Full_Adder_circuit.jpeg
"Full_Adder_circuit.jpeg")

</div>

There are no connections between crossed lines in this schematic, only
at the 'T's.

Each square box represents a Memory Bank. The ones with a "+" in it
perform the primary addition and are programmed as listed above. The
ones with a "C" in them perform the carry addition and are programmed
with the proper data shown above.

Adding the carry IN more than doubles the complexity of the circuit
since it now performs two additions. The two operands are added and the
carry is added to that result. (When building it, the carry could be
added to one of the operands first and there would be no difference.)
When either of these additions produce a carry out, it must be
propagated to the next circuit, or to the output. Therefore the two
carries must be OR'd together.

The full adder can be found in my Computer Circuits world
[here](https://app.box.com/s/h2ov4e43prvv5dqc2dvsw581vql06tsc)

## Other (temp holding)

To implement a logic compare output bits: 0 is =, 1 is \<, 2 is \>. Bit
3 could be any, such as 'complement'. program with:
1444444444444444214444444444444422144444444444442221444444444444222214444444444422222144444444442222221444444444222222214444444422222222144444442222222221444444222222222214444422222222222144442222222222221444222222222222214422222222222222142222222222222221

A subtraction circuit depends more on your numerical representation
scheme. I.e., whether you use signed/unsigned/1’s complement/2’s
complement integers. All those options make it tough to present in a
simple message reply. However, you can usually subtract by complementing
the ‘subtrahend’ and adding them. What ‘complement’ means depends on the
representation. I’ll cover subtraction in more detail when I get to it.

[Category:Electricity](Category:Electricity "wikilink")
[Category:Circuits](Category:Circuits "wikilink")
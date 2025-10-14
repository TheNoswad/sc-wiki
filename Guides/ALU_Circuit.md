---
title: ALU_Circuit
description: 
published: true
date: 2025-10-12T23:29:32.892Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:29:28.916Z
---

The central function of a computer is to perform operations on data.
This is done with an Arithmetic/Logic Unit or ALU.

This article presents an ALU that may be used to build a computer core
around or used for other calculation needs.

This shows the testing setup for the ALU:

<div style="overflow:hidden">

![ALU_setup.jpg](ALU_setup.jpg "ALU_setup.jpg")

</div>

The layout of the ALU is modular:

<div style="overflow:hidden">

![ALU_bitwise.jpg](ALU_bitwise.jpg "ALU_bitwise.jpg")

</div>

Each 'column' performs one operation and all operations are performed at
the same time, in parallel. You can see that some functions are done by
the logic gates while others use programmed memory banks. Some functions
operated on both inputs, such as the 'AND' operation. Others, such as
'[NOT](Logic_NOT_Gate "wikilink") ' only operate on one input. The Input
A is the dominant one and is always used for single operand functions.

Only one result is enabled to the output bus, at any time. The vertical
banks function as the
[multiplexer](Multiplexers_and_Demultiplexers "wikilink") for the
outputs. The opcode signal is the control to these banks and selects
which output is enabled. This parallel arrangement allows for very fast
operation.

Details on the layout:

<div style="overflow:hidden">

![ALU_basic.jpg](ALU_basic.jpg "ALU_basic.jpg")

</div>

You can see the two input busses, the output bus and the opcode signal.
The source for these are not discussed in this article. The first
picture shows a test setup where the input values and opcode are set by
the user.

[Category:Electricity](Category:Electricity "wikilink")
[Category:Circuits](Category:Circuits "wikilink")
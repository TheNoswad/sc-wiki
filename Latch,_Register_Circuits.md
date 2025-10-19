---
title: Latch,_Register_Circuits
description: 
published: true
date: 2025-10-12T23:58:51.416Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:58:47.247Z
---

Before reading this article, you should have a basic grasp of
survivalcraft electrics and understand how the [Memory
Bank](Recipaedia/Electrics/Memory_Bank.md "wikilink") works and how to program it. Also note
that in these circuits the clock input of the bank is NOT used to write
to the banks, so the ‘funniness’ of writing is not necessary.

It is always important to remember that the timing of the [memory
bank’s](Recipaedia/Electrics/Memory_Bank.md "wikilink") CLOCK input and its relationship to
other signals could be critical. It is very wise to have an
understanding of synchronous systems, such as most computers, when
designing with latches and registers.

## Introduction

A latch is a single memory location that will store one value for later
recall. They are often used with an input that changes over time and
triggered on a specific event when you want to remember what the input
was at that moment in time. They are typically used in electric circuits
to keep an input steady while it is read, or to hold an output until it
is read by another circuit, or by the user.

A register is simply a latch that can be read back by the same circuit
that set it. When latches are used in computer circuits they are often
simply called registers.

## Basic Latch

<div style="overflow:hidden">

![Latch_basic.jpg](Latch_basic.jpg "Latch_basic.jpg")

</div>

The basic latch simply locks in the value of the input whenever the
control signal goes high (a digital '1'). The bank is programmed
linearly in the '0' row so the output value is the same as the low
address input value.

To show that the ‘Latch/’ control activates on the transition, the input
connection is shown with a triangle. The “/” at the end of the name also
shows that it activates on the rising edge of the signal. The other
inputs, which are state dependent, use a square. --- To program a linear
response, put “0123456789ABCDEF” in the first row. If you need to use
the High Address input for the Data Input, put that string down the
first column, instead.

## Buffered Latch

<div style="overflow:hidden">

![Latch_Buffered.jpg](Latch_Buffered.jpg "Latch_Buffered.jpg")

</div>

The buffered latch adds the ability to disable the output and only allow
it through when the output enable control is active (digital '1'). This
works because Survivalcraft electric gates use an implicit OR in each
connection. That means any number of outputs may be wired together and
each one is effectively OR'd with all the others.

The buffered latch is able to have the output and input connected
together. The value of the input only matters when the latch control
goes to '1'. During that time, the output enable must be off
(digital'0'). This lets the latch be connected to a data bus and only be
activated when needed.

This has an internal data output for any circuitry that needs access to
the data regardless of the enable control.

## Decoded Latch

<div style="overflow:hidden">

![Latch_Decoded.jpg](Latch_Decoded.jpg "Latch_Decoded.jpg")

</div>

This circuit replaces the AND with a Memory Bank and is more typical of
a register used in a computer system. The bank is programmed to operate
the same as the AND but only when the proper value (address) is present
on the enable input. This address can be either one or both of the
address inputs depending on the circumstances.

For a full bidirectional register, the latch control must also be
address decoded and set to the same address. Simply put the linear
response ‘code’ in the row that corresponds to the address you wish to
use to read the register. Remember that the Output Enable Address input
must decode the ENTIRE address space. I.e., in a 8-bit address, you
cannot simply use the lower 4 bits alone – the upper address bits MUST
also be included. (See the decoding page.)

## Bus Based Register

In a bus based computer system, the input and output of the register
usually needs to be accessed at the same memory location. The following
circuit adds the final stage of memory decoding as an example.

<div style="overflow:hidden">

![Latch_Bused.jpg](Latch_Bused.jpg "Latch_Bused.jpg")

</div>

This way there is no separate line for the output enable and the latch
control. They both incorporate the system R/-W signal. This signal is
typically locked to the clock in a synchronous system. The last stage of
a typical address decoder is shown as well. This stage could be used to
control the timing of the latch control, if the R/-W signal does not.
This would be a part of the ‘bank select’ signal.

Note that you could save space in this circuit by using another memory
bank to replace the NOT gate and the AND gate that it feeds into. If we
assume the NOT goes into the High Address input and the decoded address
into the Low Address Input, then “000000000000000F” is programmed into
the first row.

## Uses

  - Latches are often used in video games to capture the value of some
    variable at the moment the player hits a button.
  - They are used to hold a value for display while the circuit can
    continue with other functions.
  - They may be used to stop and freeze a changing input, so it can be
    read without jitters.
  - The inputs to and output from a computer's ALU are held in
    registers.

## Notes

  - You must always remember that the latch activates only AS the latch
    control goes to '1'. This timing may be critical and the other
    inputs must be stable at that moment.

## Related Pages

[Memory Bank](Recipaedia/Electrics/Memory_Bank.md "wikilink")

[Memory Arrays](Memory_Arrays "wikilink")

[Using Analog Signals](Using_Analog_Signals "wikilink")

[RAM Circuits](RAM_Circuits "wikilink")

[Write Encoder](Write_Encoder "wikilink")

[Category:Electricity](Category:Electricity "wikilink")
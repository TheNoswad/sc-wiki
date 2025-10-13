---
title: Write_Encoder
description: 
published: true
date: 2025-10-13T00:27:53.732Z
tags: 
editor: markdown
dateCreated: 2025-10-13T00:27:49.777Z
---

## Introduction

To properly read and write to the [memory bank](Memory_Bank "wikilink"),
the clock input must be viewed as an analog input. There are three
states the clock input can be in. The first state is ‘8’hex and higher.
The second is from ‘1’hex through ‘7’hex. The third is at ‘0’hex. If
there is no connection to the rear of the bank then the second and third
state are equivalent. State 1 may be called ‘read’, state 2 called
‘write’ and the third may be just be called the ‘0’ state. Changes TO
the ‘0’ state make no change in the bank, however they may be necessary
for proper operation.

Most systems use binary (digital) signals to control memory access which
have to be converted to the correct voltages. This article tells how to
use another memory bank as a voltage converter. This may be done several
ways depending on the system needs.

## R/-W line

You can use the system R/-W signal alone as in this circuit. When the
R/-W control is low, the output will be ‘4’. This puts it in the write
state. When R/-W is high, the output will be ‘F’ to start a read. NOTE
that this circuit is very limited and will likely never be used. There
must be a write before any new location can be read and this make it
very problematic.

<div style="overflow:hidden">

![Write_Encoder_1.jpg](Write_Encoder_1.jpg "Write_Encoder_1.jpg")

</div>

Program the first line with ‘40000000FFFFFFFF’. If you need to put it in
the other address input, program that data down the first column
instead, with the ‘4’ at the top.

## Read and Write

This circuit shows the clock input as derived from separate read and
write controls. These controls may be timed to the system clock or be
asynchronous. The read or write will occur when the respective line goes
high. This circuit assumes the read control takes precedence over the
write control.

<div style="overflow:hidden">

![Write_Encoder_3.jpg](Write_Encoder_3.jpg "Write_Encoder_3.jpg")

</div>

Assuming the inputs are as shown, program the bank so line ‘F’hex is
‘4000000000000000’ to write and line ‘0’hex is ‘000000000000000F’ to
read. If they are swapped, make row ‘F’hex as ‘F000000000000000’ to read
and ‘0’ as ‘0000000000000004’ to write.

## R/-W and Clock

This circuit shows it tied to a clock. This could be the system clock,
or another control signal to time the transitions, as required by the
design. Both reads and writes are timed to the rising edge of this
clock. The bank’s clock input always goes to ‘0’ when the external clock
is low and does not have the problems of the first circuit. This is the
most common situation found in processor designs.

<div style="overflow:hidden">

![Write_Encoder_2.jpg](Write_Encoder_2.jpg "Write_Encoder_2.jpg")

</div>

The bank is programmed in row ‘F’hex with ‘400000000000000F’. If the
inputs need to be swapped, simply put that data down the first column,
with the ‘4’ at the top.

## Related Pages

  - [Memory Bank](Memory_Bank "wikilink")
  - [RAM Circuits](RAM_Circuits "wikilink")
  - [Latch, Register Circuits](Latch,_Register_Circuits "wikilink")
  - [Using Analog_Signals](Using_Analog_Signals "wikilink")

[Category:Electricity](Category:Electricity "wikilink")
[Category:Electric Chip](Category:Electric_Chip "wikilink")
[Category:Circuits](Category:Circuits "wikilink")
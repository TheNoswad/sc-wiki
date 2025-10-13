---
title: Using_Analog_Signals
description: 
published: true
date: 2025-10-13T00:22:14.867Z
tags: 
editor: markdown
dateCreated: 2025-10-13T00:22:10.705Z
---

Analog signals are an important and very useful part of electricity in
Survivalcraft. They further set SC ahead of other 'sandbox' games. The
electricity component of Survivalcraft is the most advanced feature in
all known sandbox games.

## Digital -v- Analog Signals

A digital output can only be 2 values. Either it is a 0 or a 1. This is
called a binary signal, since bi- means two. A 'pure' digital input is
one that has a specific yes/no response and that means either it does
something or it doesn't. The digital input also does not 'pass through'
an analog value.  An [LED](LED "wikilink") is an example of a pure
digital input. All the inputs on an SR latch are pure digital. When an
analog signal goes into a digital input, it will be treated as a 0 only
if it is *less than* 0.8 Volts.

An analog signal in Survivalcraft can be any of 16 values. These values
are 0 through 15. In many cases, they are called a voltage and that
voltage is then 0 \~ 1.5 Volts. Notice that since we include the value
0, that counts as one of the 16 values.

Since analog has 16 possible values it is the same as a 4-bit digital
bus. A bus is simply a group of related digital signals all going to the
same places. It's 4-bits because that's how many digital lines (or bits)
we need to show 16 different values.

The standard way of showing the 16 values of a 4-bit bus is called
"HEXIDECIMAL". This literally translates to "six plus ten", or 16\! Huh,
figures. So a Survivalcraft analog analog signal can be called a
hexidecimal signal, or hex for short. A chart showing the different ways
we can write these values, is included at the end of this section.

The last column in the chart shows how an analog input will be treated
when it goes into a digital input. Any value from '0' Hex to '7' Hex
will be a 0 digital. Any value bigger will be treated as a 1 digital. If
you look at the binary column and compare it to the "digital in" column,
you can see that the "in" column is identical to the biggest bit - the
one on the left - in the binary column. When the analog signal is read
by a **pure** digital input, it is just a copy of the 4th bit on the
bus.

Survivalcraft electrics use both types of signals but they can often be
interchanged. A digital output of '0' is the same as an analog output of
0 Volts or '0' Hex. A digital output of 1 is the same as an analog
output of 'F' Hex, NOT a '1' Hex, NOT a '8' Hex, either. A digital
output has ALL the bits set (to 1). In effect, ALL signals are analog
but digital outputs are limited to the two extremes and pure digital
inputs only look at the high bit.

HEXIDECIMAL chart

This chart shows the different ways we can show the values of the analog
signal. The voltage (decimal), binary and hex numbers in each row all
mean the *same* number. They are just different ways to say the same
thing. Binary shows the actual digital bits for that number. Hex is a
shortcut way to write that number. Voltage is decimal which is just a
way for humans to relate to that very same number. The "digital in"
column shows what that value means to a pure digital input.

` Voltage     Binary     Hex   digital`
`(decimal)                      input`
`    0.0       0000       0       0`
`    0.1       0001       1       0`
`    0.2       0010       2       0`
`    0.3       0011       3       0`
`    0.4       0100       4       0`
`    0.5       0101       5       0`
`    0.6       0110       6       0`
`    0.7       0111       7       0`
`    0.8       1000       8       1`
`    0.9       1001       9       1`
`    1.0       1010       A       1`
`    1.1       1011       B       1`
`    1.2       1100       C       1`
`    1.3       1101       D       1`
`    1.4       1110       E       1`
`    1.5       1111       F       1`

**This is technical article and is not intended for the new beginner.**
**You should already understand the basics of how the gates work before
going any further.**

## Types of Analog Signals

  -
    The term 'analog signal' is actually a misnomer. The signals aren't
    quite what electrical engineers would call analog. They combine the
    properties of both a 'true' analog signal and a digital 'bus'. This
    bus carries the information of up to 4 digital bits. (This is
    commonly called a 'nibble'. A byte is 8 digits so 4 digits was named
    a nibble.)

<!-- end list -->

  -
    The fact that they are actually 'hybrid' signals allows us to create
    some unique circuits that would be more complex otherwise. For the
    devices which do not actually take a real analog signal, it can be
    imagined that they have an implied A\>D or D\>A built into them.

They are most like a 'true' analog signal with these devices:

  -
    A\>D and D\>A converters, Battery, Hygrometer, Motion Detector,
    Photodiode, Pressure Plates, Target, Thermometer

They are hybrid signals with the following devices:

  -
    7-Segment Displays, Random Generator, Real Time Clock, Sound
    Generator

They are most like a digital bus with some devices:

  -
    4-LED, Memory Bank

The differences may only matter to the technically inclined:

  -
    If the 4-LED actually took a true analog signal, it would not
    respond in the manner which it does. Each LED reflects the *state of
    one bit* of the signal, rather than the signal *level*. If it
    responded to the level, it should have 16 LEDs instead. This does
    however, allow us to control all 4 LEDs separately with a single
    signal (bus).

<!-- end list -->

  -
    The hybrid and bus type inputs or outputs may be considered to have
    built-in A\>Ds on these inputs and D\>As on the outputs.

## Processing Analog Signals

### Signal Propagation

The analog signal will propagate through the basic gates - as described
below. These devces are:

  -
    AND, OR, XOR, NOT, DELAY

If the output signal is actually generated internal to a device, an
analog input will NOT show through to the output. These types include:

  -
    4-Bit Counter, Memory Bank, SR Latch, Truth Table

Of course, an analog signal passes freely through wires and Wire-Through
blocks.

### Input Processing

When an analog signal (actually any signal) is input to a pass-through
gate, the output is determined by the analog values of all inputs. The
gates operate on a bit-to-bit basis. That means a NOT gate will invert
each bit of the analog input. The AND, OR and XOR will perform their
functions on each bit of the inputs individually. Say, in an OR gate, an
input of "*0110*" (the 4-bit analog value) OR'd with the other input of
"*1001*" would output a "*1111*". AND and XOR are done the same way.

The benefit of this shows when one input is analog and the other is pure
digital.

  -
    In an AND gate, one digital input will act like a shutoff switch for
    an analog signal in the other input. Since a 0 digital is a "*0000*"
    analog, when you AND each bit you will get 0. When the digital input
    is 1, its analog value is "*1111*". If you AND that with the analog
    input you get the same value for the ouput. The output always
    represents the smaller of the inputs.

<!-- end list -->

  -
    In an OR gate, the digital input acts like a 'shutON' switch. When
    there is a digital 1 on one input, the output will always be 1 or
    "*1111*" regardless of what the analog input is. When the digital
    input is 0, the output will be the same value as the analog input.
    The output is always the bigger of the inputs.

<!-- end list -->

  -
    In a XOR gate, the digital input acts like a NOT gate that you can
    turn on and off. When the digital input is 1 or "*1111*", the output
    is the NOT of the analog input (each bit is inverted). When the
    digital input is 0, the output is the same as the analog input.

If both inputs are analog, the output is the function (AND OR XOR) done
on each bit. This same process is done in every case.

If you run an analog signal into any other digital input, it will act
like a digital signal. That means if it's less than '8' (or 0.8V) then
it's treated as a 0. If it's '8' or higher, it's treated as a 1. A
'pure' digital input only looks at the first, highest bit.

The only known exceptions to this rule at this time are the [Memory
Bank](Memory_Bank "wikilink") clock input and the [Sound
Generator](Sound_Generator "wikilink") tone input. These are true hybrid
inputs and actually serve two separate digital functions and depend on
the hybrid nature of the Survivalcraft electric signals to accomplish
that. See those pages for more details.

## Links

  - [Electricity Category](Special:Category:Electricity "wikilink") to
    see all the pages in the category and its sub-categories.
  - [Lefora Electrics
    Forum](http://survivalcraft.lefora.com/forums/2451984). There's more
    good tutorials and references here.

[Category:Electricity](Category:Electricity "wikilink")
[Category:Circuits](Category:Circuits "wikilink")
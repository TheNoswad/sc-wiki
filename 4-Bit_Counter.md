---
title: 4-Bit_Counter
description: 
published: true
date: 2025-10-12T23:28:59.270Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:28:55.227Z
---

__NOEDITSECTION__

## Description   (From [Recipaedia](Recipaedia "wikilink") )

*An electric 4 bit counter with increment, decrement, reset and overflow
detection capabilities (useful for chaining counters). Outputs its
current value at the top via an analog signal. You can use
analog-to-digital converter to extract the actual 4 bits, if needed.
Signal on the right input increments the counter. Signal on the left
input decrements it. Both increment and decrement wrap aroung when reach
above 15 or below 0, in which case an overflow signal is generated at
the bottom output. The back input (use wire-through-block element to
access it) resets the counter to 0. Plus, minus and reset input are
activated by rising edge of the signal. The counter can be mounted on
any vertical surface and rotated to desired orientation.*

## Crafting

Use 2 copper ingots and 5 germanium crystals to craft the 4-bit counter.
You get 4 counters chips.

<div style="overflow:hidden">

![4-Bit_Counter.png](4-Bit_Counter.png "4-Bit_Counter.png")

</div>

## Hooking it up

There are 3 inputs to the counter and 2 outputs. Typically only 1 of the
inputs and the analog output will be used in most applications.
Typically.

The 3 inputs + (INC), - (DEC) and RESET are common digital signals and
can be controlled by a switch or pressure pad or any other digital
output. The reset input is on the back of the chip so you have to use a
wire-through block to get to it.

The main output - C is analog and must be fed to an analog input of
another device. It has a value from 0 - F which increases by one every
time the + input activates (the rising edge). It decreases by one when
the - input goes high. When the reset input goes high, this output goes
to 0.

The O (OVERFLOW) output is also a digital signal and can energize a LED
or a light or activate a door or be fed to any other digital input. If
the value of the counter tries to go less than 0 OR greater than F then
the Overflow output will go high (until any input changes \< must be
verified \>). This may be used to 'chain' counters to let you count to
much bigger numbers. This output would go into the next counter's input.

## Uses

The 4-bit counter is typically used for --- counting.

You could use it in a circuit that only lets someone enter a room 3
times then it will drop a column of sand in front of the door.

Use it with a [date clock circuit](Real_Time_Clock "wikilink") to count
the number of days you have been in a mine.

They are a necessary component in combination or [PIN type
locks](Advanced_PIN_lock "wikilink").

## Applications

### Short Counting

You may need the counter to only cycle through a smaller number and
stop. This may be done with a few added gates. For an UP ONLY counter,
add an AND gate in series with the + input, feed the counter output to a
Memory Bank which was programmed as a compare and take the output of the
bank to the other side of the AND. Program the bank to disable the AND
when you reach the maximum number of the count.

<div style="overflow:hidden">

![Short_counter.jpg](Short_counter.jpg "Short_counter.jpg")

</div>

If you short the count on an UP/DOWN counter, you must also limit the
down count so it will stop at '0'. Use the same technique but program
the bank differently. The counter in the image above has both limits.

### Extended Up/Dn Counting

The overflow output may be used to extend the counter for a dedicated up
OR down counter but cannot be used in a single Up/Dn counter because it
does not distinguish between an UP overflow and a DOWN underflow. The
following circuit does this.

<div style="overflow:hidden">

![15269204041881.jpg](15269204041881.jpg "15269204041881.jpg")

</div>

The memory banks are programmed to detect the overflow (carry) and
underflow (borrow) conditions. For example when the new count is '0' and
we are counting UP, the counter has overflowed (carry) and the bank on
the right sends an UP count to the next higher stage (top center of the
image). The memory bank for the borrow condition is programmed
similarly. The two OR gates are necessary to allow the counter to update
its output before the carry or borrow is determined.

<div style="overflow:hidden">

![15269213426951.jpg](15269213426951.jpg "15269213426951.jpg") This
design may be 'chained' to make any length UP/DN counter with one
caveat. The UP or DN input must stay steady while the entire counting
chain is updated. Each additional stage adds another 2 'tics' to the
delay. A two stage (8-bit) counter takes 3 tics while a four stage
(16-bit) counter takes 7 tics.

In this build, programmable delays set to the minimum delay time were
used rather than OR gates.

</div>

## Notes

  - For more advanced counters which do NOT use this chip, see [Counter
    Circuits](Counter_Circuits "wikilink").
  - Despite Recipaedia's description, 4-bit Counters can be placed on
    horizontal surfaces too since v1.29.

## History

The 4-bit counter was added in ver. 1.23

[Category:Electrics](Category:Electrics "wikilink") [Category:Electric
Chip](Category:Electric_Chip "wikilink")
[Category:Electricity](Category:Electricity "wikilink")
[Category:Crafted](Category:Crafted "wikilink")
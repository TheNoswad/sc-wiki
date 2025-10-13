---
title: Memory_Bank
description: 
published: true
date: 2025-10-13T00:02:28.303Z
tags: 
editor: markdown
dateCreated: 2025-10-13T00:02:23.919Z
---

__NOEDITSECTION__

## Description   (From [Recipaedia](Recipaedia "wikilink") )

*Writeable memory bank containing 256 4-bit words. The memory can be
addressed using two 4-bit address lines placed on the left and right. If
an address line is not connected, it's assumed to be zero. Value stored
in the memory bank under the specified address can be read at the top
output. Bottom input is used as a clock in a similar fashion to SR
latch. If the clock line is not connected, reads are immediate. To write
to the memory bank, supply the value to be written on the back input
(you must use wire-through-block). The write is triggered by setting
clock input to a low voltage between 0.1 and 0.7 volts (a value of 0.8
and larger will trigger a read). The contents of memory block can be
manually edited by tapping edit button when block is held in hand (see
warning below) or looked at. Can be placed on any surface and rotated to
desired orientation.*

## Connections

There are a total of 5 connections to the memory. The output is on 'top'
and the two address signals are on the 'sides' - the least significant
to the single dot and the most significant to the double dots. The clock
input goes in where the arrow or dart is, on the 'bottom' and the data
input is through the back.

<div style="overflow:hidden">

![Memory_pins.jpg](Memory_pins.jpg "Memory_pins.jpg")

</div>

## Crafting

Crafting requires 6 [germanium crystals](Germanium_Crystal "wikilink")
and 1 [copper ingot](Copper_Ingot "wikilink"). You get 4 Memory Banks. 

<div style="overflow:hidden">

![Memory_Bank-0.png](Memory_Bank-0.png "Memory_Bank-0.png")

</div>

## Understanding It

You can think of the memory like a big BINGO card, or Battleships
playing field. "G-4" defines one location in either game. The letters
would come from one address line while the numbers come from the other
one. The memory bank is a much bigger card than that:

` ||0 1 2 3 4 5 6 7 8 9 A B C D E F|`
`0||X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|`
`1||X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|`
`2||X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|`
`3||X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|`
`4||X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|`
`5||X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|`
`6||X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|`
`7||X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|`
`8||X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|`
`9||X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|`
`A||X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|`
`B||X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|`
`C||X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|`
`D||X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|`
`E||X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|`
`F||X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|X|`

This table is the same as you will get when manually editing the memory.
The numbers across the top represent all the analog values for the low
address (one dot). The numbers down the side represent all the analog
values for the high address (two dots). The spot where the two lines
cross is the location you can read from.

When you put any value on the address inputs, the memory finds the
location where those addresses cross. It  copies the data (X) from that
location to the output.

If you connect the clock input to anything, the memory will wait to copy
that data.

Any one address can also be programmed electrically. Writing to the
memory is quite complex and is best to be avoided when possible.

## How to Use It

#### Addressing

You can only access a single location in the bank at a time. Only one of
the X's in the chart above. You need two signals to find one X. Why two?
Because each signal  in Survivalcraft can represent 4 bits, or 0 to 15
(analog 0 to F). The chart makes it easier to see.

The inputs on left and right of the chip are the two address lines. The
one with a single dot sets the 4 low bits of the address, and the values
listed across the top of the chart. The one with two dots sets the 4
high bits. These are listed down the left of the chart.

If you need less than 16 elements from the memory bank, you only need
one address input (typically the low bits) and can leave the other
disconnected. That will give you 4 bit addressing, i.e. up to 16
locations.

#### Reading

The value stored in the memory bank is available through the top output
and is present immediately if a clock is NOT used. As soon as the
addresses change, the output will change to the new value.

The clock input is optional and works the same way as in [SR
latch](SR_Latch "wikilink"). If it is connected, the address lines will
only be read at the rising edge of the clock signal. At all other times
the output of the memory bank will keep showing the last addressed
location, no matter what is currently supplied to address lines. This is
useful for synchronous or timed circuits.

#### Writing

In the rare case where you need to write to the memory block, you must
use the data input (i.e. the one accessible when you place the memory
bank on wire-through-block element). The value supplied on this input
will be written at the address shown by address lines on the rising edge
of the clock input, which must be 0.7V or less. Anything above 0.7V will
cause a synchronous read, as described above. Since there IS a
connection to the clock input, all reads must be 'synchronous'. Example
circuits are presented below...

#### Editing

Memory block is manually editable. When you hold a memory block in your
hand (or look at a mounted one from close distance), the sneak button
will change into edit button, as seen in the picture below.

\* \* \* WARNING \* \* \*

Do NOT edit the bank when it's in-hand if you are in any survival mode.
The game has a bug that will delete all banks in the selected slot
EXCEPT ONE\!. Once a bank is programmed, it becomes unique and cannot
share an inventory slot with any other item. But you can hold a full
stack of unprogrammed banks. If you then edit the stack as a whole, the
game gets confused and will turn the entire stack into just one single
(programmed) bank. Losing an entire stack of memories in cruel mode can
be very frustrating\!

\* \* \* \* \*

Tap that button and an editing window will open up where you can enter
the data. See the picture. Each entry in the middle is one memory
location and is located by the numbers across the top and left side,
much like a BINGO card. The numbers across the top represent the low 4
bits of the address (going into the single dot) and the ones down the
left are the high 4 bits (the double
dots).![Memory_Bank.png](Memory_Bank.png "Memory_Bank.png")

If you are only using one address signal and it's the low one, the only
locations that matter are the first row across. If however, you have to
use ONLY the high 4 bit signal, then you can only access the first
COLUMN down the left.

To edit the memory, tap on the row you need to change and an entry
dialog box will open showing the current contents of that row. Changing
the contents from this point is device dependant and may not be the same
for everyone. Sorry.

The 'Linear" button will let you fill in the entire 256 locations in one
entry. This can be very error prone to enter by hand, but you can use
this way to copy-paste the entire chart at once. Copy it from another
app and you should be able to paste it into this box.

## Applications

The value in memory banks will stay valid even when the Player moves
very far away.

  - The most obvious use is to store data for later access. Applications
    for this are many - one could be to have certain numbers show on a
    7-segment display when certain switches are active.
  - Useful in active or simulated displays.
  - Can control 4 digital devices according to the input of up to 8
    different signals.

<!-- end list -->

  - Can be a decoder - translate any analog value to any other value at
    random or by function.

### Analog Latch

A latch is used to 'capture' a reading on the data input. This is used
where a signal may be changing over time and you want to get the value
at one specific time. There is an article dedication to using the memory
bank as a [latch or register.](Latch,_Register_Circuits "wikilink")

### Analog Comparator

A comparator is simply a 'gate' that outputs a digital 1 when both
inputs are exactly the same. This is the same as an inverted XOR, for
pure digital inputs.

The two analog signals are fed to the two address inputs. The clock is
left open. The memory's data output is (usually) a digital signal. The
memory must be programmed with the compare function. The basic compare
has the memory programmed to output a digital 1 (hex 'F') only when the
low address line is the same as the high address line. The memory image
for this is:

`  || 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 || 8 | 9 | A | B | C | D | E | F ||`

`0 || F |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`1 ||   | F |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`2 ||   |   | F |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`3 ||   |   |   | F |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`4 ||   |   |   |   | F |   |   |   ||   |   |   |   |   |   |   |   ||`
`5 ||   |   |   |   |   | F |   |   ||   |   |   |   |   |   |   |   ||`
`6 ||   |   |   |   |   |   | F |   ||   |   |   |   |   |   |   |   ||`
`7 ||   |   |   |   |   |   |   | F ||   |   |   |   |   |   |   |   ||`
`8 ||   |   |   |   |   |   |   |   || F |   |   |   |   |   |   |   ||`
`9 ||   |   |   |   |   |   |   |   ||   | F |   |   |   |   |   |   ||`
`A ||   |   |   |   |   |   |   |   ||   |   | F |   |   |   |   |   ||`
`B ||   |   |   |   |   |   |   |   ||   |   |   | F |   |   |   |   ||`
`C ||   |   |   |   |   |   |   |   ||   |   |   |   | F |   |   |   ||`
`D ||   |   |   |   |   |   |   |   ||   |   |   |   |   | F |   |   ||`
`E ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   | F |   ||`
`F ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   | F ||`

All locations that are blank are actually filled with '0's. They are
left out here for clarity. You can see that where the low address value
(top) is the same as the high address value (left), the output will be
'F', or a digital 1. Wherever they are NOT the same, a zero is output.

You can copy the number below and paste it, if you like.

`F0000000000000000F0000000000000000F0000000000000000F0000000000000000F0000000000000000F0000000000000000F0000000000000000F0000000000000000F0000000000000000F0000000000000000F0000000000000000F0000000000000000F0000000000000000F0000000000000000F0000000000000000F`

This same circuit can be used for other compare functions, such as "less
than" or "greater or equal" by simply changing the memory's 'matrix'.
With more complicated programming, you could even have a "close-to"
function output. This could be something like, "the output is 'F' when
the inputs are exactly the same and it is '8' if the difference is 1 or
'4' if the difference is 2 or '0' if it's more". That's just one example
of a more complicated compare function and is usually called 'fuzzy'
math.

### PLD

Any memory bank can be used as a general purpose "Programmable Logic
Device". This means that it can be used to replace a huge amount of
individual logic gates. Each and every possible combination of all 8
address lines (the 2 address inputs) can be programmed to output any
pattern on the 4 output bits. Programming the memory for a general use
PLD can be very tricky. Engineers using even small PLDs usually have a
special program to determine the matrix values from their function's
equations. Each application of course, is unique so examples are not
offered.

### Addition Module

One specific application of the PLD is as an addition module. One memory
bank can be programmed to do (unsigned) addition on two inputs. Each
input can only be 3 bits wide, however. Two 3 bit values can add up to a
4 bit result. Since there are only 4 output bits, three bit values are
the most that can be added. The 4th output bit can be used as a carry
into a higher stage addition module, to let you add larger numbers.
Addition modules are 'chained' that way. The data matrix for a basic
adder is below:

`  || 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 || 8 | 9 | A | B | C | D | E | F ||`

`0 || 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 ||   |   |   |   |   |   |   |   ||`
`1 || 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 ||   |   |   |   |   |   |   |   ||`
`2 || 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 ||   |   |   |   |   |   |   |   ||`
`3 || 3 | 4 | 5 | 6 | 7 | 8 | 9 | A ||   |   |   |   |   |   |   |   ||`
`4 || 4 | 5 | 6 | 7 | 8 | 9 | A | B ||   |   |   |   |   |   |   |   ||`
`5 || 5 | 6 | 7 | 8 | 9 | A | B | C ||   |   |   |   |   |   |   |   ||`
`6 || 6 | 7 | 8 | 9 | A | B | C | D ||   |   |   |   |   |   |   |   ||`
`7 || 7 | 8 | 9 | A | B | C | D | E ||   |   |   |   |   |   |   |   ||`
`8 ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`9 ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`A ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`B ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`C ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`D ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`E ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`F ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`

Only 1/4 of the array is used because we are not using the highest bit
of the inputs and the rest of the values can all be left at '0'. To see
how the added works, let's find for instance, 5 + 4. First find 5 at the
top and 4 on the left. Where they cross is the output value, of 9.

In order to 'chain' the addition blocks, a 'carry in' bit must be used.
It has to be one of the inputs' 4th bits but it can be on either input
if the memory is programmed for it. Remember that any input not
connected is assumed to be '0'.

If the carry is '1'. it means we have to add a 1 to the result. A carry
can only be a 1 in computer numbers (binary). So we take the quarter we
already have, add one to each location and paste it where either 4th bit
is a '1'.

This chart looks like this:

<u>`  || 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 || 8 | 9 | A | B | C | D | E | F ||`</u>

`0 || 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 || 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 ||`
`1 || 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 || 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 ||`
`2 || 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 || 3 | 4 | 5 | 6 | 7 | 8 | 9 | A ||`
`3 || 3 | 4 | 5 | 6 | 7 | 8 | 9 | A || 4 | 5 | 6 | 7 | 8 | 9 | A | B ||`
`4 || 4 | 5 | 6 | 7 | 8 | 9 | A | B || 5 | 6 | 7 | 8 | 9 | A | B | C ||`
`5 || 5 | 6 | 7 | 8 | 9 | A | B | C || 6 | 7 | 8 | 9 | A | B | C | D ||`
`6 || 6 | 7 | 8 | 9 | A | B | C | D || 7 | 8 | 9 | A | B | C | D | E ||`
<u>`7 `</u>`||`<u>` 7 | 8 | 9 | A | B | C | D | E `</u>`||`<u>` 8 | 9 | A | B | C | D | E | F `</u>`||`
`8 || 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 ||   |   |   |   |   |   |   |   ||`
`9 || 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 ||   |   |   |   |   |   |   |   ||`
`A || 3 | 4 | 5 | 6 | 7 | 8 | 9 | A ||   |   |   |   |   |   |   |   ||`
`B || 4 | 5 | 6 | 7 | 8 | 9 | A | B ||   |   |   |   |   |   |   |   ||`
`C || 5 | 6 | 7 | 8 | 9 | A | B | C ||   |   |   |   |   |   |   |   ||`
`D || 6 | 7 | 8 | 9 | A | B | C | D ||   |   |   |   |   |   |   |   ||`
`E || 7 | 8 | 9 | A | B | C | D | E ||   |   |   |   |   |   |   |   ||`
`F || 8 | 9 | A | B | C | D | E | F ||   |   |   |   |   |   |   |   ||`

Here's the linear stream for it:

`01234567123456781234567823456789234567893456789A3456789A456789AB456789AB56789ABC56789ABC6789ABCD6789ABCD789ABCDE789ABCDE89ABCDEF123456780000000023456789000000003456789A00000000456789AB0000000056789ABC000000006789ABCD00000000789ABCDE0000000089ABCDEF00000000`

Remember that the number input can only be from 0 through 7 and repeats
under the carry portion. Where the matrix has a 'D' input for example,
the number input is actually a '5' but the carry is also a +1. If take
the previous example of 5 + 4 and assume the carry is +1, we will go to
the 'D' at the top (which is 5 +carry) and follow it down until it
crosses the '4' row. (Carry only applies to one input.) The answer is
'A', or 10. (5 + 4) + 1 = 10

The biggest difficulty we have to build this, is separating out the bits
from the 'analog' signals. Analog signals naturally contain 4 bits of
data. We can only add 3 at a time with this module. If we're adding more
than three bits, that means we have to split out the bits in the analog
signal and rearrange them to fit the adder. That also means that the
adders HAVE to be chained and that means the 4th output bit is actually
a carry-out. This bit also has to be split out from the analog output
signal.

To split the bits out, we use an A\>D to separate the bits, rearrange
them and use a D\>A to recombine them into an analog signal. This has to
be done to each address input as well as the data output.

Addition of other 'types' of numbers, such as signed integers, BCD,
exponentials, etc. gets very complex and should never be needed in any
SC setting.

## Clock Input Use

This section presents circuits to control the clock input when you wish
to write electrically to the memory.

If you need to write to the memory but do not need synchronous reads,
the circuit is quite simple. You will have a digital control signal that
tells when to write to the memory. This signal needs to be 0 to write
and 1 to read. If it's the other way, just add a NOT in series. You will
also need a fixed voltage reference that is 0.1V to 0.7V. One easy way
to do this is to use a battery and program it to 0.7V. Then you just
feed this into one side of an OR gate and the write control into the
other input. Then feed the OR gate output into the memory clock input.
This makes the clock input value either 'F' (to read) or '7' (to write).

The basic logic gates pass through an analog signal. [This (technical)
page](Using_Analog_Signals "wikilink") explains it but you don't need to
know that in order to make it. It basically means that when the button
is pressed (goes to 1), the battery voltage will be sent to the memory
clock input. When the button is off or 0, the clock input is 1.

See the picture:

<div style="overflow:hidden">

![Memory_write_ckt.jpg](Memory_write_ckt.jpg "Memory_write_ckt.jpg")

</div>

This circuit gets more complicated if you need to write yet still have
regular, clocked synchronous operation. The write voltage must be
disabled separately from the clock input and this really just requires
an additional AND gate.

<div style="overflow:hidden">

![Memory_write_circuit_B.jpg](Memory_write_circuit_B.jpg
"Memory_write_circuit_B.jpg")Two control signals are used here.

</div>

WRITE ENABLE lets the write (low) voltage pass through to the memory.

SYSTEM CLOCK is normally the memory read signal. The memory reads from
the address when this goes high.

For a write to the memory, the WRITE ENABLE must be 1 while the clock is
low. The write address must be ready before the OR's output goes (low)
to the write voltage. This circuit can be used if you want to program a
memory in adventure mode or from a distance (a control panel?).

## Further Information

More information on creating the clock input signal can be found [on
this page.](Write_Encoder "wikilink") It provides simpler ways to
convert the voltages.

[Category:Electricity](Category:Electricity "wikilink")
[Category:Electrics](Category:Electrics "wikilink") [Category:Electric
Chip](Category:Electric_Chip "wikilink")
[Category:Crafted](Category:Crafted "wikilink")
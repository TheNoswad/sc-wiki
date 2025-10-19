---
title: PLD_Design
description: 
published: true
date: 2025-10-13T00:05:36.757Z
tags: 
editor: markdown
dateCreated: 2025-10-13T00:05:32.061Z
---

## Introduction

The [memory bank](../Recipaedia/Electrics/Memory_Bank.md "wikilink") can be used as a general
purpose programmable logic device, or PLD. That means it can take up to
8 binary (digital) inputs, combine them using any possible logical
formula and output up to 4 bits of binary data. This makes it a very
powerful and compact logic processor.

This article is very advanced and you need a solid background in logic
design and a thorough understanding of the memory bank to get the most
from it. An understanding of matrix mathematics is also helpful.
Fortunately, the bank will be used in asynchronous mode so we won’t need
to work with the clock input of the bank – for now…

In effect, four complex logic functions may be performed, each one
corresponding to one of the outputs. The only limitation is in the
number of discrete inputs required for these functions. As long as the
total is 8 or less, one bank will be sufficient.

This article will use a manual method to compute the final bank program.
The manual method uses a graph to represent the data matrix of the
memory bank. There are automated PLD design tools that satisfy our needs
but they are generally available to electrical engineers and require
learning their use. If you already have these, feel free to experiment
with them. If you develop a useable solution, please contact this wiki
admins to see about adding that information to this page.

An example problem will be used to illuminate the process. This is a
‘real-world’ problem that the author used in a world build. Links to
the project are presented at the end.

## Bin to Hex to Bin

Note that there is the issue of getting the I/O in and out of the bank
in analog(hex) form. Usually these inputs and outputs are digital
(binary) signals and must be combined into and separated from the hex
form required by the memory bank. The A\>D and D\>A chips are used for
that.

This bulk of this article concerns developing the internal program for
the memory bank used as the PLD. The end of it will have a section on
using the A\>D and D\>A to convert the signal formats. This conversion
will necessarily increase the space needed for a PLD circuit. However, a
PLD can replace a large number of discrete gates and you should still
see a space savings. Plus most logic design errors will not require a
physical redesign, just reprogramming of the PLD.

## Process Steps

We will use a manual process which follows straightforward steps. Not
surprisingly since it is a logical function, itself.

1.  Set up the equations or gate diagrams
2.  Determine the total I/O needs
3.  Assign the inputs and outputs
4.  Express each function separately in the data matrix
5.  Combine the several functions in each matrix cell
6.  Use that data to program the memory bank

## Setting up the equations

The first step is to determine the functions required. All functions
must be expressed in Boolean algebra or by using logic gates. Any and
all standard logic gates may be used, and any number of them can be
incorporated. The total number of final results must be 4 or less, since
that’s the most the bank can output. This means up to four discrete
functions may be performed in a single memory bank.

Once your logic functions are determined, count the number of unique
inputs. This must be 8 or less, in order to use a single bank. If there
are more, the functions must be separated to keep the total inputs less
than 9. In many cases, output functions use some of the same inputs.
These inputs are only counted once. In other cases, a single function
may require more than 8 inputs by itself. In that case, additional
processing will be needed. An additional PLD, or discrete logic gates
are necessary to partially process some of the inputs to create a single
partial result. Such partial result will then be applied to the final
PLD to keep the input count sufficiently low.

This article will assume that the required functions fall within the
input limitations. Additional processing as mentioned above is simply
repeating this process in additional steps.

### Example functions

In the example, four functions are required and they use 6 of the
inputs. The written functions are as follows:

1.  ImgInc = (Cmax AND (Cmax XOR CMdelay))
2.  ImgRst = (restart OR (Imax AND NOT(loop)))
3.  ColRst = (restart OR CMdelay)
4.  ColInc = ((NOT(ImgInc) AND (SysClk AND (loop OR NOT(Imax)))

So, the four outputs are clearly ImgInc, ImgRst, ColInc and ColRst. The
inputs are Cmax, CMdelay, Imax, SysClk, restart and loop. The
particulars of what all these names mean is irrelevant. They have
meaning only to the system they are used in. We don’t need to know that
in order to complete the design.

There is one more function used by the overall system and it will be
helpful to discuss it briefly. The CMdelay input derives from the Cmax
signal and is just a delayed version of it. Since there is no delay
inside the memory bank, that delay is performed externally and thus
requires another input.

Also note that in the last function, one of the other outputs is called
as an input – ImgInc. This is completely acceptable since the ImgInc is
NOT a separate input. In all regards this is not a very complex design
specification. There are still two unused inputs and the logic needs
could be much more intricate. It does provide a reasonable example
without being too simplistic.

The logic diagram for those function is shown:

<div style="overflow:hidden">

![PLD_diagram.jpg](PLD_diagram.jpg "PLD_diagram.jpg")schematic

</div>

This image shows the delay gate and the SysClk source, both of which are
external to the PLD, but helpful to understand the design. The long
names of the I/O may also be seen.

## Assigning the inputs and outputs

The inputs and outputs may be assigned at random, or there may be an
external reason to assign them to particular bits. Once the equations
are determined, we need to have all I/O assigned before we can combine
them. If there is no external need for certain assignments, then it
could be totally random. There is no difference internally and the
calculations will have little difference, no matter how they are
assigned.

### Example assignments

In this example, the inputs were assigned as shown below. Some inputs
were assigned according to physical layout needs. The rest were assigned
at random.

INPUT LOW:

`   Bit0 = SysClk`

`   Bit1 = loop`

`   Bit2 = - -`

`   Bit3 = restart`

INPUT HIGH:

`   Bit0 = Cmax`

`   Bit1 = CMdelay`

`   Bit2 = Imax`

`   Bit3 = - -`

OUTPUT:

`   Bit0 = ColRst`

`   Bit1 = ColInc`

`   Bit2 = ImgRst`

`   Bit3 = ImgInc`

## Express the functions as matrix

The functions and assignments are used to fill in the data matrix of the
memory bank. This is where your knowledge of logic design is crucial.
You must understand how the input bits are represented by the locations
in the matrix. This article cannot provide that education. Each output
will first be filled into a separate matrix.

Only one function will be shown set-by-step. It would be quite lengthy
to repeat the process for each function. Some education may be obtained
by this process however, it is strongly recommended to have a solid
understanding before proceeding.

The function numbered 2 above will be implemented here. It was expressed
as “ImgRst = (restart OR (Imax AND NOT(loop)))”. This function uses 3
inputs. It is output on bit 2, so everywhere in the matrix it is
expressed, we place a ‘4’hex. A ‘1’ on bit 2 represent a ‘4’ in
hexadecimal notation.

Where the ‘4’s are placed defines the function. All the INPUTLOW bits
are represented across the top of the matrix while all the INPUTHIGH
bits down the side. Therefore, all possible combinations of all input
bits may be achieved.

### Example

The example function is “ImgRst = (restart OR (Imax AND NOT(loop)))”. We
will start with the innermost function and build our way to the end. The
innermost function is the NOT(loop). We will put a ‘4’hex in each
location that the loop input is ‘0’. The loop input is present at
INPUTLOW-bit1. The matrix is shown:

`                 INPUT LOW`
`INPUT | 0 1 2 3 4 5 6 7 8 9 A B C D E F`
`HIGH  |--------------------------------`
`  BBBB| 0 0 0 0 0 0 0 0 1 1 1 1 1 1 1 1  -  BIT3`
`  IIII| 0 0 0 0 1 1 1 1 0 0 0 0 1 1 1 1  -  BIT2`
`  TTTT| 0 0 1 1 0 0 1 1 0 0 1 1 0 0 1 1  -  BIT1`
`  3210| 0 1 0 1 0 1 0 1 0 1 0 1 0 1 0 1  -  BIT0`
`------|--------------------------------`
`0|0000| 4 4     4 4     4 4     4 4   `
`1|0001| 4 4     4 4     4 4     4 4   `
`2|0010| 4 4     4 4     4 4     4 4   `
`3|0011| 4 4     4 4     4 4     4 4   `
`4|0100| 4 4     4 4     4 4     4 4   `
`5|0101| 4 4     4 4     4 4     4 4   `
`6|0110| 4 4     4 4     4 4     4 4   `
`7|0111| 4 4     4 4     4 4     4 4   `
`8|1000| 4 4     4 4     4 4     4 4   `
`9|1001| 4 4     4 4     4 4     4 4   `
`A|1010| 4 4     4 4     4 4     4 4   `
`B|1011| 4 4     4 4     4 4     4 4   `
`C|1100| 4 4     4 4     4 4     4 4   `
`D|1101| 4 4     4 4     4 4     4 4   `
`E|1110| 4 4     4 4     4 4     4 4   `
`F|1111| 4 4     4 4     4 4     4 4   `

The next enclosing function is an AND between the above function and
Imax. Imax is present at INPUTHIGH-bit2, so we can start by putting a
‘4’hex everywhere that bit is ‘1’.

`                  INPUT LOW`
`INPUT | 0 1 2 3 4 5 6 7 8 9 A B C D E F`
`HIGH  |--------------------------------`
`  BBBB| 0 0 0 0 0 0 0 0 1 1 1 1 1 1 1 1  -  BIT3`
`  IIII| 0 0 0 0 1 1 1 1 0 0 0 0 1 1 1 1  -  BIT2`
`  TTTT| 0 0 1 1 0 0 1 1 0 0 1 1 0 0 1 1  -  BIT1`
`  3210| 0 1 0 1 0 1 0 1 0 1 0 1 0 1 0 1  -  BIT0`
`------|--------------------------------`
`0|0000|`
`1|0001|`
`2|0010|`
`3|0011|`
`4|0100| 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4`
`5|0101| 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4`
`6|0110| 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4`
`7|0111| 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4`
`8|1000|`
`9|1001|`
`A|1010|`
`B|1011|`
`C|1100| 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4`
`D|1101| 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4`
`E|1110| 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4`
`F|1111| 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4`

Now, to perform the AND function, we take the two previous matrices and
put a ‘4’hex ONLY where both matrices have a ‘4’hex. Thus the result is
“Imax AND NOT(loop)”.

`                   INPUT LOW`
`INPUT | 0 1 2 3 4 5 6 7 8 9 A B C D E F`
`HIGH  |--------------------------------`
`  BBBB| 0 0 0 0 0 0 0 0 1 1 1 1 1 1 1 1  -  BIT3`
`  IIII| 0 0 0 0 1 1 1 1 0 0 0 0 1 1 1 1  -  BIT2`
`  TTTT| 0 0 1 1 0 0 1 1 0 0 1 1 0 0 1 1  -  BIT1`
`  3210| 0 1 0 1 0 1 0 1 0 1 0 1 0 1 0 1  -  BIT0`
`------|--------------------------------`
`0|0000|    `
`1|0001| `
`2|0010| `
`3|0011| `
`4|0100| 4 4     4 4     4 4     4 4   `
`5|0101| 4 4     4 4     4 4     4 4   `
`6|0110| 4 4     4 4     4 4     4 4   `
`7|0111| 4 4     4 4     4 4     4 4   `
`8|1000| `
`9|1001| `
`A|1010|  `
`B|1011 `
`C|1100| 4 4     4 4     4 4     4 4   `
`D|1101| 4 4     4 4     4 4     4 4   `
`E|1110| 4 4     4 4     4 4     4 4   `
`F|1111| 4 4     4 4     4 4     4 4   `

The outer most operation is the OR. This is implemented by putting a
‘4’hex wherever EITHER of the operands are true. Since one operand
is the restart input, first place a ‘4’hex in every location wherever
that bit is ‘1’. The restart bit is present at INPUTLOW-bit3. The result
is as shown:

`                  INPUT LOW`
`INPUT | 0 1 2 3 4 5 6 7 8 9 A B C D E F`
`HIGH  |--------------------------------`
`  BBBB| 0 0 0 0 0 0 0 0 1 1 1 1 1 1 1 1  -  BIT3`
`  IIII| 0 0 0 0 1 1 1 1 0 0 0 0 1 1 1 1  -  BIT2`
`  TTTT| 0 0 1 1 0 0 1 1 0 0 1 1 0 0 1 1  -  BIT1`
`  3210| 0 1 0 1 0 1 0 1 0 1 0 1 0 1 0 1  -  BIT0`
`------|--------------------------------`
`0|0000|                 4 4 4 4 4 4 4 4`
`1|0001|                 4 4 4 4 4 4 4 4`
`2|0010|                 4 4 4 4 4 4 4 4`
`3|0011|                 4 4 4 4 4 4 4 4`
`4|0100|                 4 4 4 4 4 4 4 4`
`5|0101|                 4 4 4 4 4 4 4 4`
`6|0110|                 4 4 4 4 4 4 4 4`
`7|0111|                 4 4 4 4 4 4 4 4`
`8|1000|                 4 4 4 4 4 4 4 4`
`9|1001|                 4 4 4 4 4 4 4 4`
`A|1010|                 4 4 4 4 4 4 4 4`
`B|1011|                 4 4 4 4 4 4 4 4`
`C|1100|                 4 4 4 4 4 4 4 4`
`D|1101|                 4 4 4 4 4 4 4 4`
`E|1110|                 4 4 4 4 4 4 4 4`
`F|1111|                 4 4 4 4 4 4 4 4`

To implement the OR, that matrix is combined with the previous one. In
any place that EITHER is ‘4’hex, a ‘4’hex is placed. The final matrix is
as follows:

ImgRst = (restart OR (Imax AND NOT(loop)))

`                  INPUT LOW`
`INPUT | 0 1 2 3 4 5 6 7 8 9 A B C D E F`
`HIGH  |--------------------------------`
`  BBBB| 0 0 0 0 0 0 0 0 1 1 1 1 1 1 1 1  -  BIT3`
`  IIII| 0 0 0 0 1 1 1 1 0 0 0 0 1 1 1 1  -  BIT2`
`  TTTT| 0 0 1 1 0 0 1 1 0 0 1 1 0 0 1 1  -  BIT1`
`  3210| 0 1 0 1 0 1 0 1 0 1 0 1 0 1 0 1  -  BIT0`
`------|--------------------------------`
`0|0000|                 4 4 4 4 4 4 4 4 `
`1|0001|                 4 4 4 4 4 4 4 4`
`2|0010|                 4 4 4 4 4 4 4 4`
`3|0011|                 4 4 4 4 4 4 4 4`
`4|0100| 4 4     4 4     4 4 4 4 4 4 4 4`
`5|0101| 4 4     4 4     4 4 4 4 4 4 4 4`
`6|0110| 4 4     4 4     4 4 4 4 4 4 4 4`
`7|0111| 4 4     4 4     4 4 4 4 4 4 4 4`
`8|1000|                 4 4 4 4 4 4 4 4`
`9|1001|                 4 4 4 4 4 4 4 4`
`A|1010|                 4 4 4 4 4 4 4 4`
`B|1011|                 4 4 4 4 4 4 4 4`
`C|1100| 4 4     4 4     4 4 4 4 4 4 4 4`
`D|1101| 4 4     4 4     4 4 4 4 4 4 4 4`
`E|1110| 4 4     4 4     4 4 4 4 4 4 4 4`
`F|1111| 4 4     4 4     4 4 4 4 4 4 4 4`

Now we have the final matrix for the one function which is output on
bit2. We still have to derive the matrices for the other functions. When
doing so, we would use the proper value for the bit position of that
function. I.e., bit0 uses a ‘1’, bit1 uses a ‘2’, bit2 used a ‘4’ and
bit 3 will use a ‘8’hex. The final matrices for the other functions in
the example are shown:

BIT0 = ColRst = (restart OR CMdelay)

`                  INPUT LOW`
`INPUT | 0 1 2 3 4 5 6 7 8 9 A B C D E F`
`HIGH  |--------------------------------`
`  BBBB| 0 0 0 0 0 0 0 0 1 1 1 1 1 1 1 1  -  BIT3`
`  IIII| 0 0 0 0 1 1 1 1 0 0 0 0 1 1 1 1  -  BIT2`
`  TTTT| 0 0 1 1 0 0 1 1 0 0 1 1 0 0 1 1  -  BIT1`
`  3210| 0 1 0 1 0 1 0 1 0 1 0 1 0 1 0 1  -  BIT0`
`------|--------------------------------`
`0|0000| 1 1 1 1 1 1 1 1`
`1|0001| 1 1 1 1 1 1 1 1`
`2|0010| 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1`
`3|0011| 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1`
`4|0100| 1 1 1 1 1 1 1 1`
`5|0101| 1 1 1 1 1 1 1 1`
`6|0110| 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1`
`7|0111| 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1`
`8|1000| 1 1 1 1 1 1 1 1`
`9|1001| 1 1 1 1 1 1 1 1`
`A|1010| 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1`
`B|1011| 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1`
`C|1100| 1 1 1 1 1 1 1 1`
`D|1101| 1 1 1 1 1 1 1 1`
`E|1110| 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1`
`F|1111| 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1`

BIT1 = ColInc = ((NOT(ImgInc) AND (SysClk AND (loop OR NOT(Imax)))

`                  INPUT LOW`
`INPUT | 0 1 2 3 4 5 6 7 8 9 A B C D E F`
`HIGH  |--------------------------------`
`  BBBB| 0 0 0 0 0 0 0 0 1 1 1 1 1 1 1 1  -  BIT3`
`  IIII| 0 0 0 0 1 1 1 1 0 0 0 0 1 1 1 1  -  BIT2`
`  TTTT| 0 0 1 1 0 0 1 1 0 0 1 1 0 0 1 1  -  BIT1`
`  3210| 0 1 0 1 0 1 0 1 0 1 0 1 0 1 0 1  -  BIT0`
`------|--------------------------------`
`0|0000|   2   2   2   2   2   2   2   2`
`1|0001| `
`2|0010|   2   2   2   2   2   2   2   2`
`3|0011|   2   2   2   2   2   2   2   2`
`4|0100|       2       2       2       2 `
`5|0101| `
`6|0110|       2       2       2       2`
`7|0111|       2       2       2       2`
`8|1000|   2   2   2   2   2   2   2   2`
`9|1001| `
`A|1010|   2   2   2   2   2   2   2   2`
`B|1011|   2   2   2   2   2   2   2   2`
`C|1100|       2       2       2       2`
`D|1101| `
`E|1110|       2       2       2       2`
`F|1111|       2       2       2       2`

BIT3 = ImgInc = (Cmax AND (Cmax XOR CMdelay))

`                  INPUT LOW`
`INPUT | 0 1 2 3 4 5 6 7 8 9 A B C D E F`
`HIGH  |--------------------------------`
`  BBBB| 0 0 0 0 0 0 0 0 1 1 1 1 1 1 1 1  -  BIT3`
`  IIII| 0 0 0 0 1 1 1 1 0 0 0 0 1 1 1 1  -  BIT2`
`  TTTT| 0 0 1 1 0 0 1 1 0 0 1 1 0 0 1 1  -  BIT1`
`  3210| 0 1 0 1 0 1 0 1 0 1 0 1 0 1 0 1  -  BIT0`
`------|--------------------------------`
`0|0000| `
`1|0001| 8 8 8 8 8 8 8 8 8 8 8 8 8 8 8 8`
`2|0010| `
`3|0011| `
`4|0100| `
`5|0101| 8 8 8 8 8 8 8 8 8 8 8 8 8 8 8 8`
`6|0110| `
`7|0111| `
`8|1000| `
`9|1001| 8 8 8 8 8 8 8 8 8 8 8 8 8 8 8 8`
`A|1010| `
`B|1011| `
`C|1100| `
`D|1101| 8 8 8 8 8 8 8 8 8 8 8 8 8 8 8 8`
`E|1110| `
`F|1111| `

## Combining the matrices

Once the matrices are complete for each function, we need to combine
them for the complete data to be programmed. As long as they are done as
described, using the hex values for the output bit locations, simply add
the numbers in the same location of each matrix. Place the sum at the
same location in the final matrix.

### Example final matrix

Taking the sum of each location in the matrix, we get the following
final matrix:

`                  INPUT LOW`
`INPUT | 0 1 2 3 4 5 6 7 8 9 A B C D E F`
`HIGH  |--------------------------------`
`  BBBB| 0 0 0 0 0 0 0 0 1 1 1 1 1 1 1 1  -  BIT3`
`  IIII| 0 0 0 0 1 1 1 1 0 0 0 0 1 1 1 1  -  BIT2`
`  TTTT| 0 0 1 1 0 0 1 1 0 0 1 1 0 0 1 1  -  BIT1`
`  3210| 0 1 0 1 0 1 0 1 0 1 0 1 0 1 0 1  -  BIT0`
`------|--------------------------------`
`0|0000| 0 8 0 9 0 8 0 9 0 8 0 9 0 8 0 9`
`1|0001| 0 8 0 9 0 8 0 9 0 8 0 9 0 8 0 9`
`2|0010| 0 8 0 9 0 8 0 9 0 8 0 9 4 C 4 D`
`3|0011| 0 8 0 9 0 8 0 9 0 8 0 9 4 C 4 D`
`4|0100| 0 8 0 9 0 8 0 9 0 8 0 9 0 8 0 9`
`5|0101| 2 8 2 B 0 8 0 9 2 8 2 B 2 8 2 B`
`6|0110| 0 8 0 9 0 8 0 9 0 8 0 9 4 C 4 D`
`7|0111| 2 8 2 B 0 8 0 9 2 8 2 B 6 C 6 F`
`8|1000| 5 D 5 D 5 D 5 D 5 D 5 D 5 D 5 D`
`9|1001| 5 D 5 D 5 D 5 D 5 D 5 D 5 D 5 D`
`A|1010| 5 D 5 D 5 D 5 D 5 D 5 D 5 D 5 D`
`B|1011| 5 D 5 D 5 D 5 D 5 D 5 D 5 D 5 D`
`C|1100| 5 D 5 D 5 D 5 D 5 D 5 D 5 D 5 D`
`D|1101| 7 D 7 F 5 D 5 D 7 D 7 F 7 D 7 F`
`E|1110| 5 D 5 D 5 D 5 D 5 D 5 D 5 D 5 D`
`F|1111| 7 D 7 F 5 D 5 D 7 D 7 F 7 D 7 F`

### Simple short-cut

Rather than write out separate matrices for each output, one short-cut
is to make a 3-D matrix. That is one where each output is represented in
the same box, so instead of having four separate matrices, we have four
entries in each box. This also makes it easier to add up each box for
the final value.

The example below is NOT the same equations as used above - they are
from the same project but reflect updated functions.

<span style="font-size:5px;">

`R   L C |  0 |  0 |  0 |  0 |  0 |  0 |  0 |  0 | 1  | 1  | 1  | 1  | 1  | 1  | 1  | 1  | OmDel`
`S R o l |  0 |  0 |  0 |  0 | 1  | 1  | 1  | 1  |  0 |  0 |  0 |  0 | 1  | 1  | 1  | 1  | OffMx`
`E u o o |  0 |  0 | 1  | 1  |  0 |  0 | 1  | 1  |  0 |  0 | 1  | 1  |  0 |  0 | 1  | 1  | CmDel`
`T n p k |  0 | 1  |  0 | 1  |  0 | 1  |  0 | 1  |  0 | 1  |  0 | 1  |  0 | 1  |  0 | 1  | ColMx`
`--------|-------------------------------------------------------------------------------|`
`0 0 0 0 |    |    | 8  | 8  |    |    | 8  | 8  |    |    | 8  | 8  |    |    | 8  | 8  |`
`        |    |    |    |   1|    |    |    |   1|    |    |    |   1|    |    |    |   1|`
`0 0 0 1 |    |    | 8  | 8  |    |    | 8  | 8  |    |    | 8  | 8  |    |    | 8  | 8  |`
`        |    |    |    |   1|    |    |    |   1|    |    |    |   1|    |    |    |   1|`
`0 0 1 0 |    |    | 8  | 8  |    |    | 8  | 8  |    |    | 8  | 8  |   4|   4| 8 4| 8 4|`
`        |    |    |    |   1|    |    |    |   1|    |    |    |   1|    |    |    |   1|`
`0 0 1 1 |    |    | 8  | 8  |    |    | 8  | 8  |    |    | 8  | 8  |   4|   4| 8 4| 8 4|`
`        |    |    |    |   1|    |    |    |   1|    |    |    |   1|    |    |    |   1|`
`0 1 0 0 |    |    | 8  | 8  |    |    | 8  | 8  |    |    | 8  | 8  |    |    | 8  | 8  |`
`        |    |    |    |   1|    |    |    |   1|    |    |    |   1|    |    |    |   1|`
`0 1 0 1 |    |    | 8  | 8  |    |    | 8  | 8  |    |    | 8  | 8  |    |    | 8  | 8  |`
`        | 2  |    | 2  | 2 1|    |    |    |   1| 2  |    | 2  | 2 1| 2  |    | 2  | 2 1|`
`0 1 1 0 |    |    | 8  | 8  |    |    | 8  | 8  |    |    | 8  | 8  |   4|   4| 8 4| 8 4|`
`        |    |    |    |   1|    |    |    |   1|    |    |    |   1|    |    |    |   1|`
`0 1 1 1 |    |    | 8  | 8  |    |    | 8  | 8  |    |    | 8  | 8  |   4|   4| 8 4| 8 4|`
`        | 2  |    | 2  | 2 1|    |    |    |   1| 2  |    | 2  | 2 1| 2  |    | 2  | 2 1|`
`1 0 0 0 |   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|`
`        |   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|`
`1 0 0 1 |   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|`
`        |   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|`
`1 0 1 0 |   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|`
`        |   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|`
`1 0 1 1 |   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|`
`        |   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|`
`1 1 0 0 |   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|`
`        |   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|`
`1 1 0 1 |   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|`
`        | 2 1|   1| 2 1| 2 1|   1|   1|   1|   1| 2 1|   1| 2 1| 2 1| 2 1|   1| 2 1| 2 1|`
`1 1 1 0 |   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|`
`        |   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|   1|`
`1 1 1 1 |   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|   4|   4| 8 4| 8 4|`
`        | 2 1|   1| 2 1| 2 1|   1|   1|   1|   1| 2 1|   1| 2 1| 2 1| 2 1|   1| 2 1| 2 1|`

</span>

## Program the bank

The memory bank may be programmed with that matrix several ways.
Probably the easiest and least error-prone is to turn it into a single
string with a text editor. First make sure that each location has a
value in it – especially all the ‘0’s. Then remove all white spaces. It
will then be a single, long string. If you can, verify that it’s 256
characters long. Any other length means there’s been an error somewhere.

Select and copy that string to the clipboard. It’s good practice to make
sure there is a ‘hard copy’ of this string so you may want to paste it
into a text document for safety.

Open the game and edit the memory bank that will be used as the PLD.
Select ‘LINEAR’ and open the edit window. Paste the clipboard into that
window and ‘OK’ it.

You now have a PLD programmed with your own functions. It may seem like
a lot of work but this PLD could potentially replace many discrete logic
gates and will take up a lot less space.

## The complete circuit

As discussed briefly in the beginning, the inputs and output will
probably need to be converted into and out of hex (analog) form. The
A\>D and D\>A are provided for this purpose. At most, this means that a
complete PLD circuit needs 4 chips – the PLD, 2 D\>A chips and 1 A\>D
chip. If the functions that the PLD replaces need 4 or fewer chips, it
is likely overkill. However, you may even still see a space savings,
depending on how the discrete gates must be wired.

The resources needed for converting the signals are actually quite
small. For each conversion, you only need the gate, one wire-through
block and probably 4 other blocks – one to accept each digital line. It
also takes up little space, just a 3 x 3 x 2 area. Getting the binary
(digital) signals to and from the converters and PLD may be the most
difficult part of it all. That is totally dependent on the system
architecture and physical layout.

Furthermore, as mentioned above, there is also the issue of design error
or upgrade. If all necessary inputs are routed into the PLD and all
necessary outputs routed from the PLD then any change in logic needs can
be done by changing the program of the PLD, rather that adding, removing
or re-wiring discrete gates. This could be a huge benefit in more
complex systems. As an example, in the example system used, the author
routed several other signals to the PLD inputs, expecting a possible
need to use them. However as logic design progressed, it became apparent
they were not. Since they are already present, there is no penalty to
keep them available in case a future upgrade may need them.

## Synchronous Mode

It was said at the beginning that the clock input will not be needed and
that’s true. However, there may be cases in which the PLD outputs must
only change at certain times. The clock input may be used to accomplish
this. Only the read function is needed so there is no concern with the
pseudo-analog nature of writing to the bank.

## Related Pages

  - [Memory Bank](../Recipaedia/Electrics/Memory_Bank.md "wikilink")
  - link to example world
  - perhaps mathematics websites?

[Category:Electricity](Category:Electricity "wikilink")
[Category:Circuits](Category:Circuits "wikilink")
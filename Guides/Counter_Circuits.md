---
title: Counter_Circuits
description: 
published: true
date: 2025-10-12T23:42:43.903Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:42:39.470Z
---

Survivalcraft provides a convenient single-block binary up/down counter.
However, there are many instances where a counter with more features are
needed. In particular the [4-Bit Counter](4-Bit_Counter "wikilink")
makes no distinction between carry and borrow since it only has an
overflow output. That lack makes it unsuitable as the basis of extended
(more than 4 bits) up/down counters. This article will explain other
ways to make counters and why and where they may be used, as well as the
advantages and disadvantages of these alternate designs.

## Random Sequence(s) Counter

This counter is simple in design and has the greatest flexibility.
However, it must be carefully programmed. As shown, there are two
sequence inputs but this can easily be increased to four. Each button
steps the counter through a specific sequence of outputs. Each sequence
can be unique and they don't have to be sequential numbers, either.
I.e., one sequence could be 1-7-4-A-C-6-2-9-7-1. The total number of
different outputs must be 16 or less and you cannot repeat any number in
the sequence. You also have to be careful that one sequence doesn't
include a number that may put another sequence in a state it can't
recover from. This would only happen in 'strange' sequences. Any number
that one sequence can generate must be covered by every sequence that
might follow it.

One advantage to that circuit is it easily makes short sequence, up/down
counters. The circuit shown can be used this way. Note that there are
two connections to each button. This takes advantage of the 'isolated'
outputs they have. If these signals are outputs from other gates, you
will have to use an 'OR' gate to combine them.

<div style="overflow:hidden">

![Random_Counter.jpg](Random_Counter.jpg "Random_Counter.jpg")

</div>

The output does not change until the CLOCK input is active. Therefore
this is a "synchronous" counter. For an "asynchronous" counter that
relies solely upon the UP and DN controls, see below.

### Programming

The circuit shown has 2 buttons (sequences) and they are meant to be UP
and DOWN. Since they are connected to the 1 and 3 bit inputs on the
A\>D, we will only program the corresponding rows of the Memory Bank.
Let's assume we want a counter to run 0-1-2-3-4 up and 4-3-2-1-0 down.

The UP line translates to a "1" input to the bank and the DOWN line to a
"4", so only these rows (high addresses) are used. The low addresses
represent the current counter output so in each row, we just place the
next output in each sequence. For the UP function (row '1'), under the 0
we will place a 1. Under the 1, a 2. Under the 3, a 4 and under the 4, a
0. This way the count will start over and keep cycling.

The DOWN function (row '4') is programmed similarly but with decreasing
numbers.. Under the 0, we place a 4, under the 1, a 0 and so on. That's
all the programming the bank needs.

The adjustable delay gate is fed to the clock input of the bank and this
will "latch" the output when it goes high. Otherwise the output would
change when the input does and it would just keep changing constantly.
By using the clock input, the output will only change when the clock
first goes active. The delay gate must be set to a delay of 3 ticks, or
0.03 seconds because the clock must wait for the other inputs to be
stable. If you put the 'OR' gate in, it only needs to be 2.

## Updated (small) Random Counter

This counter is an upgrade of the above sequencer. It only needs 2
components and can count in any sequence programmed into it. The
sequence may be a 'regular' count, such as 1, 2, 3, ... or it could
count by -2's or even any other unique sequence.

The sequence is controlled by the function input. It uses no clock since
the counter will update at each 'pulse' of the function input. This
means the function input must return to '0' after each update.

<div style="overflow:hidden">

![15268297055381.jpg](15268297055381.jpg "15268297055381.jpg")

</div>

The upper memory bank does the counting/sequencing function while the
lower one controls the clocking of the first bank. The function input
(from the left) is pulsed briefly with the code for the type of count to
be performed. This is usually +1/-1/+2/-2 but any sequence can be
implemented.

This function code is input to the counter bank but its output does not
change yet since the clock input is connected. The code is also sent to
the clock generator bank. This bank simply outputs an 'F' whenever the
function code is not '0'. This 'F' triggers the read of the counter bank
and the counter's output is then updated. The output of the clock gen is
a single 'tic' delayed from the function code which gives the system
time to calculate the next value of the counter bank. The clock input
then latches that value when the read is activated via the clock input.

This circuit is the fastest (and smallest) 'discrete' counter/sequencer
possible as its new value is ready 2 tics after the function code is
active. The function code may remain active for a random time but must
be returned to '0' before another code is input. The output will remain
steady until a new function code is activated.

There is no provision for presetting this counter and at least 1
function code should be programmed to always output a '0' so the counter
may be reset. If all the counter does is +1/-1 then the single-chip
[4-Bit Counter](4-Bit_Counter "wikilink") may do the job but this
circuit does not require a separate reset input and can 'count' in any
fashion.

The negative is that it does not include carry/borrow provisions so is
limited to the 4-bit hex (analog) output range.

## Presettable, Bus-based Counter

Many times a counter needs to be started from a specific value. The
[4-Bit Counter](4-Bit_Counter "wikilink") in the game cannot be preset
to a value. The circuit here not only allows an initial value to be set,
it also includes buffers that allow it to be connected to a data bus.
The bus is expected to carry the preset value when loading is needed and
it can read the counter's output when the output buffer is enabled.

<div style="overflow:hidden">

![Preset_Bus_Counter.jpeg](Preset_Bus_Counter.jpeg
"Preset_Bus_Counter.jpeg")

</div>

This is the schematic for the circuit. As you can see it's fairly
simple. There are three buffers (AND gates) and two Memory Banks.

The bank labeled "count" holds the counter output value. The current
value is always available at the "Count Out" signal. When this value is
needed to be carried on the bus, the O.E. control must be set to '1'.
This bank is programmed in the first line only, with: 0123456789abcdef

The bank labeled "+1" provides for incrementing the "count" bank. For
every output value of the count bank, the +1 bank is programmed to
output that value +1. If the 'Inc Sel' signal is active then the output
from the +1 bank is at the input of the count bank. When the 'Pulse'
signal goes high, this value is locked into the count bank. The output
of the count bank then increases by 1 and a normal count is achieved.
Note that since the clock input to the banks are "edge-triggered" the
change will NOT feed back into the bank and cause unstable changes. The
+1 bank is programmed with: 123456789abcdef0 Note that each value is +1
from its location. That's how the +1 is performed.

The counter can be set to any value present on the data bus in addition
to normal counting. The 'Load Sel' signal must be held high while the
'Pulse' control goes high. The Count bank will then hold that value and
any further counting will be done from that value.

### Variations

There can be many variations on this circuit. The O.E. buffer may not be
needed at all, if this circuit is not fed to a data bus. The other
buffers could be implemented with additional memory banks to allow the
control signals to be a combined 'analog' signal. This may make the
layout simpler in some cases. Then a single analog control signal runs
to both buffer banks. (The banks would be programmed as demultiplexers.)

#### Fixed Presets

If you don't need to preload a random value but a specific starting
value, both select buffers may be removed. Only a single control signal
is needed to tell the circuit whether to count or to load and this
signal may be sent to the H input on the +1 bank. This bank would then
hold the fixed preset value in another location, in addition to the +1
row given above. Which row the preset value goes in would depend on how
the set/count signal is created.

If we assume a digital control signal and a '0' on this signal tells it
to count normally, then a '1' on this signal would prepare the circuit
to load the preset value. In this case, the row-0 value is the same as
given above, and the preset value will be programmed into every space in
the 'F' row.

As an example, let's assume that we want a preset of '2'. Then the
bank's complete program would be:

`123456789abcdef0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000002222222222222222`

This idea may even be expanded further to include up to 15 different
possible load values. Which value is loaded would depend on the value of
the control input.

A -1 count bank could be included, or a -2, or a +3, etc. Each one could
be a separate bank, controlled by a single digital signal.

Or they may be incorporated into a single bank that uses an encoded
control signal. The possibilities are nearly unlimited. We would then
have a fully programmable, variable sequence state-machine. The next
state is set within the bank and can output any hex value for any
current state at the one input and the 'program sequence' present at the
other bank input. The memory bank programming is all that is needed to
change this behavior.

## Loadable Up/Down Counter

The last example is of a complete, loadable up/down counter unit. This
circuit can be daisy-chained to any length desired (within reason and
the limits of Survivalcraft electrics) and is very flexible. However, it
is also the most complicated. It is intended to be connected to a data
bus and will also supply an unbuffered, steady output. This output can
be used to address a section of memory and will function as a Stack
Pointer or Program Counter. The local (steady) outputs are in hex
(analog) form as well as the data bus I/O and change only in response to
the rising edge of the clock.

This is a ‘ripple’ counter meaning that a finite amount of time is
required for all the stages to update once the count changes. Counters
with more stages will require more time to reach a stable condition. The
circuit is designed to minimize this time and a single clock is common
to all stages. Thus, it should be able to operate properly with high
clock rates. A four stage counter (16 bits) has been tested to a clock
speed of 80 ms, or 12.50 Hz. Shorter counters will operate faster. A two
stage counter operates at least to a 40 ms, or 25 Hz speed.

Following is the circuit diagram of one stage. The signals going to the
next (higher) stage are all at the top. Note that the bits of the data
bus are NOT shared between the stages, so a dotted line is shown as a
reminder.

<div style="overflow:hidden">

![Preset_count_full.jpg](Preset_count_full.jpg
"Preset_count_full.jpg")

</div>

### Controls

There are several inputs to the counter. There are four inputs that
interact - two separate inputs for counting up and down, a LOAD input
and a clock input. When either the up or down input is set, the counter
will increase or decrease on the next rising edge of the clock. This
change will ripple through the circuit to update all sections. If the
load input is set, then the data present on the bus will be loaded into
the counter on the next rising edge of the clock. The load input takes
precedence over the up or down controls. If both the up and down inputs
are high then the count will not change. There is an output enable
control input. When this is high, the counter’s outputs will be
presented to the data bus. It is assumed that the size of the counter
does not exceed the size of the data bus. If that is not the case,
additional circuitry will be required to select the different portions
of the counter.

### Internal Operation

The bank labeled ‘L’ is the core of the counter. This holds the current
count value and is essentially a latch circuit. It is programmed with
the linear function. All clock inputs to each stage are connected
together. This ensures that the outputs will change at the same time.
The bank labeled ‘+/-1’ computes the next value to be loaded in the
latch. The current value is input to one side (L) and the other side has
the command input. This command incorporates both the UP and DOWN
control in a single hex (analog) signal. This is done to greatly
simplify the circuitry but requires the two controls to be combined
through a D\>A chip, or other means. The programming expects the UP
control to be input as the bit3 and DOWN as bit2 on this input. These
may be changed as needed but the bank’s programming must be modified
accordingly. To clarify the programming, the +/- bank’s output will be
equal to the latch output +1, when only the UP control is positive. The
+/- bank’s output will be equal to the latch output -1, when only the
DOWN control is positive. For all other values of the up/down input, the
+/- bank’s output will be equal to the latch output, and no change to
the latch will happen when its clock input rises. The ‘C/B’ bank
determines whether a carry or borrow will be needed from the next higher
stage. The latch output (of its current stage) goes into one of its
inputs while the +/-1 function feeds into the other. This lets it detect
whether the current stage will overflow or underflow with the next clock
pulse and it will supply the +/-1 control to the next higher stage,
accordingly. The discrete gates at the bottom of the schematic control
the input to the latch. As long as the LOAD control is high, the +/-1
bank’s output is disconnected from the latch and the data bus is fed to
the latch. On the next clock rising edge, this data will be loaded into
the latch. The AND gate at the top of the diagram is a buffer to the
data bus. The latch output is sent to the bus as long as the OUTPUT
ENABLE control is high.

### Options and Notes

  - The NOT gate and the AND gate it feeds could be combined into a
    single memory bank, to save space.
  - There are many other possibilities available with this setup. You
    could create +/-2 counts or even non-linear functions. This article
    will not cover those cases.
  - If your system needs the UP count to take precedence over the DOWN
    count, that program is provided below. Also given is the opposing
    program (DOWN over UP). The main code assumes that if both are set,
    this indicates an error condition and no change will take place.
  - If the counter does not need to be read by the bus, the top AND gate
    is not required and the physical layout will be simplified.
  - It is possible to disable the +/-1 bank’s output differently and
    eliminate some gates, by incorporating the load control in the +1/-1
    control. This is left as an exercise for the reader, if desired.
  - Typically, a Program Counter only requires the UP function. In this
    case, that control may be binary (digital) and fed directly to the
    +/-1 bank. That bank’s program will be simplified and is also
    provided below.
  - This counter could be operated in an asynchronous mode with one
    minor addition. Instead of using a system clock, the three (or two)
    control inputs may be ‘OR’d together, followed by a short delay.
    That signal would then be fed to the clock input to cause an update
    any time one of the control signals goes active. This may be
    desirable for a Stack Pointer or a Program Counter.

### Programs

These are the ‘programs’ to be put into the several memory banks. They
are provided here so they may be copied by the device running
Survivalcraft and pasted directly in the game. The procedure to do this
is described in the [Memory Bank](Memory_Bank "wikilink") article. All
programs assume the address inputs are assigned as described above. If
they are swapped, the data matrix (grid) must be ‘inverted’. This is not
covered here.

The ‘L’ bank has a basic linear function and uses only the first line:
0123456789ABCDEF

The ‘+/-1’ bank selects the next state of the latch. This assumes bit
assignments as detailed above:

`0123456789ABCDEF000000000000000000000000000000000000000000000000F0123456789ABCDE000000000000000000000000000000000000000000000000123456789ABCDEF00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000`

`   For UP control dominance, use:`
`0123456789ABCDEF000000000000000000000000000000000000000000000000F0123456789ABCDE000000000000000000000000000000000000000000000000123456789ABCDEF0000000000000000000000000000000000000000000000000123456789ABCDEF0000000000000000000000000000000000000000000000000`

`   For DOWN control dominance, use:`
`0123456789ABCDEF000000000000000000000000000000000000000000000000F0123456789ABCDE000000000000000000000000000000000000000000000000123456789ABCDEF0000000000000000000000000000000000000000000000000F0123456789ABCDE000000000000000000000000000000000000000000000000`

For a binary (digital) UP ONLY bank, use:

`0123456789ABCDEF00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000123456789ABCDEF0`
`   This is the same as putting the first row (‘0’) as:`
`   0123456789ABCDEF and the last row (‘F’) as:`
`   123456789ABCDEF0`

The ‘C/B’ bank determines the carry or borrow to the next stage:

`0000000000000000000000000000000000000000000000000000000000000000400000000000000000000000000000000000000000000000000000000000000000000000000000080000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000`
`   This is the same as putting row ‘4’ as:`

4000000000000000 and row ‘8’ as: 0000000000000008

## 16-bit Function Code Counter

The above circuit can be expanded to 16-bits. The following circuit is
an example. Also, rather than having separate control inputs for the
various functions, this circuit uses a single hex signal input that
indicates the required function. The total delay from function code
change to a valid, latched output is 5 tics.

Compared to the previous circuit, the functions of the discrete gates
are being taken up by memory banks. In particular, the input select -
the AND gates and the INVerter at the bottom are replaced with 2 banks.
We can then feed the function code directly into the bank and let the
bank do any decoding we need. Also, the Output Enable AND gate in the
top left corner is not included. It may be added if the output is
connected to a bus.

<div style="overflow:hidden">

![Fxn_Cntr.jpg](Fxn_Cntr.jpg "Fxn_Cntr.jpg")

</div>

This circuit can count up or down (by any number up to 15) and be preset
to any given value. A total of 16 functions could be implemented.
Usually Reset, Load, +1, +2, +0, -1, -2 are sufficient.

### Operation

This is essentially an expanded version of the previous circuit with the
changes stated above and a few more. There is no clock input to control
the latch. Instead, the latch control is generated internally to allow
all functions to be initiated by a single function code input. Also, the
load control is incorporated into the function code (a single hex
signal).

As long as the function code is "Idle", no change is called for and the
counter will stay in its current state as long as needed. The 'count'
input enable is activated but the +/- banks simply pass it through. The
Dec bank does not output a latch signal so the current value just stays
as it is.

When the function calls for a 'count' (any), the 'Count' input enables
are activated and the counter banks begin computing the new value. The
'Dec' bank outputs an 'F' in time to latch the first hex digit. The OR
gates latch the next stages as they are calculated. (A delayed, common
latch control was tried but something in SCE caused the delay time to
become excessive so a chained latch was devised.) The new, latched value
is ready to be read 5 tics after the function code activates. (The
function code input must be held steady at least this long.)

If the 'reset' code is presented, all input enables are disabled and the
+/- banks output a steady '0' which is latched and becomes the current
counter value ('0000').

If the 'load' code is presented, the preset input enables are activated,
allowing the new value to the +/- banks. These banks will simply pass
this value on to the latches so the load value is latched and becomes
the current counter value.

### Use

### Programming the Banks

The memory banks implement the function denoted by the code input. As an
example, the memory programs listed below implement these functions:

`0 = Idle`
`1 = +1`
`2 = -1`
`5 = +2`
`6 = -2`
`8 = Load Preset`
`F = Reset (load '0000')`

We will assume the layout and connections as shown in the schematic. All
function codes are connected to the High-order input while the parameter
is connected to the Low-order input. This makes laying out the bank
programs easier.

#### Input Enables

There are two sets of input selects (or Enables) - the count feedback
input and the preset input. The preset input is only active for the
function code '8'. According to the schematic, the function is input to
the H order input, so all other lines in the bank must be '0 and the
line for an '8' is filled in linearly. That is, it's "0123456789ABCDEF",
so the output simply follows the input but ONLY when the function code =
'8'.

The other set of input selects enables the current count to be the
input. The same (linear) function must be entered for all function codes
that are "counts", i.e., codes = '1', '2', '5' and '6'. The idle code
also has this input enabled.

#### \+/-

These are the banks that do the 'counting'. They each have a function
input in addition to the counter value input. When the function input
says to +1, the bank is programmed to output (1 + the current value).
The other functions are programmed similarly. For example, a -1 function
line will look like: "F0123456789ABCDE". If the parameter is '0', the
bank outputs 'F', etc. When the function is '8', the +/- banks just
follow the input, like the input enables. When it is 'F', these banks
force all '0's for output, resetting the counter.

#### C/B

These banks compute whether a carry or borrow is required from the next
higher stage. Each line must be programmed uniquely for the function it
is assigned to. For example, when we want to +1 and the current value is
'F', we will send a carry (+1) to the next stage. When we want to -2, a
borrow (-1) must be sent if the current value is either '0' or '1'
because both will need to borrow from the higher stage.

Note that the 'codes' sent to the next stage do NOT have to be the same
as the function input codes. The programs listed DO have them the same
but this is only so the first-stage C/B bank may be programmed the same
as the higher-order ones.

#### Lat

These are latches and only follow the input value, just like the input
enables. Only the connection is different. Since there is nothing
connected to the High-order input, it is always '0' and we only need to
program the '0' line. It is programmed with the linear function, like
the enables. The difference is that with the clock input connected, the
output does not change until the clock signal activates. This gives the
"latch" function.

#### Enc

This single bank just converts the various function codes into a single,
binary value. When the function is 'Idle', it outputs a '0'. For any
other code, it outputs an 'F'. Thus, the first line is
"0FFFFFFFFFFFFFFF". No other line matters since there is nothing
connected to the High-order input.

#### The programs:

The final memory bank programs are listed here so they can be
copy/pasted easily. The entire 256 entry is given for completeness.

Ena (Load)

Ena (Count)

\+/-

C/B

Lat

Enc

[Category:Electricity](Category:Electricity "wikilink")
[Category:Circuits](Category:Circuits "wikilink")
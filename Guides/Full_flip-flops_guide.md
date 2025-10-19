---
title: Full_flip-flops_guide
description: 
published: true
date: 2025-10-12T23:49:50.074Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:49:46.016Z
---

## **Logic Gates Combinations and flip-flops**

*This is the part of logic elements guide. To see Logic Gates guide, go
[at this page](../Recipaedia/Electrics/Full_logic_gates_guide.md "wikilink").*

In electronics, a flip-flop or latch is a circuit that has two stable
states and can be used to store state information. This guide unites
logic gates combinations - from NAND to JK master-slave. It is mostly
made by JustPlaying.

Logic NOR Gate.jpg|Logic NOR Gate Logic NAND Gate.jpg|Logic NAND Gate
Logic XNOR Gate.jpg|Logic XNOR Gate

Logic Gates are usually combined with a NOT Gate - to improve usability
of the certain gate. NOT gate just invertes the final signal coming from
the Gate. Here are the combinations -

  - AND + NOT = **NAND**
  - OR + NOT = **NOR**
  - XOR + NOT = **XNOR**

### **T flip-flop**

T flip-flop changes the ouput giving "1" after every button press. It
can be used in many adventure maps.

Tflip_tut1.jpg|T flip-flop, front side Tflip_tut2.jpg|T flip-flop,
back side

### **JK flip-flop**

JK flip-flop behaves like normal SR Latch, untill both inputs (J and K,
Set and Reset) are ON. Then it will negate the state it has in memory.
So if the last state was "1" when both inputs are ON the output will be
0 and vice versa. JK flip-flop (unlike SR Latch) is made just with clock
input connected. Again, the flip-flop will "read" the states on its
inputs just with the rising edge in the clock input.

JKflip_tut1.jpg|Both inputs are OFF, output is OFF JKflip_tut2.jpg|J
input (=set) is ON, output is ON JKflip_tut3.jpg|K input (=reset) is
ON, output is OFF JKflip_tut5.jpg|Both inputs are ON, output negates
the last saved state (that was OFF, look at previous picture)
JKflip_tut6.jpg|Both inputs are ON, output negates the last saved state
(that was ON, look at the previous picture)

### **JK Master-Slave**

JKmaster_tut5.jpg|JK master-slave, front side JKmaster_tut6.jpg|JK
master-slave, back side

JK master-slave is made from two JK flip-flops. JK master-slave has two
inputs - J and K on the first JK flip flop (called master). JK
master-slave has one output - on the second JK flip-flop (called slave).

Normal JK flip-flop (with clock connected) will "read" the signals on J
and K only with **rising edge** of the signal on clock input. JK
master-slave (unlike the normal) will "read" the signals on J and K only
with **rising edge** of signal AND **falling edge** of signal on clock
input (you need both - rising and falling edge - to "read" the signal on
input J and K).

Maybe it's too hard to understand, here are pics with the step numbers -
(you should know that the input is the switch on the left side, clock is
the switch in the hole)

JKmaster_tut.jpg|\#1 - input (J and K) is 0, clock is 0, output is also
0 JKmaster_tut2.jpg|\#2 - input (J and K) is switched to 1, but clock
is still 0, so the output is 0 JKmaster_tut3.jpg|\#3 - input (J and K)
is still 1, clock input switched to 1 (rising edge), but output still 0
JKmaster_tut4.jpg|\#4 - input (J and K) is still 1, clock is switched
to 0 (falling edge), output finaly 1

Under the first SR Latch should be also AND gate, but it doesn't seem to
be necessary.

### **[SR Latch](../Recipaedia/Electrics/SR_Latch.md "wikilink")**

This is the gate with S and R on it, it is also the first (and only)
flip-flop added into the game.

  - It has 3 inputs

Set input (S) Reset input (R) And Clock input (^)

Since this gates has many features I shall cut it up a bit.

**The Set Input (S)**

*Where is the set input?* It is at the side where the **S** is at.

*What does it do?* It sets a signal to be stored in its memory and it
will give off that stored signal

*What if I turn off the set input?* Nothing will happen. Since the
signal is stored in its memory, it will still give off a signal

SR_tut.jpg|Switch connected to the Set input SR_tut3.jpg|Set is ON,
SRLatch stores 1, output is 1 - ON SR_tut5.jpg|Set is OFF, but the
Latch still have 1 in memory, so the output is still 1

**The reset input (R)**

*Is there any way to remove the stored signal?* Yes. Turn on the Reset
Input.

*Where is the Reset Input?* Over where the **R** is.

*What about the clock input?* You see. The clock input makes the SRLatch
recieve the signals (on Set and Reset) just with the rising edge of
signal on the clock input. "Rising edge" means change 0 -\> 1.

*What?* The clock input will stop any signal of set and reset unless it
senses a signal.

### **D latch**

Dlatch_tut3.jpg|D Latch, back side Dlatch tut.jpg|D Latch, front side

D latch may be considered like a *one-input synchrounous SR Latch* D
latch's function looks similar to T flip-flop's - it also has two
outputs, one input and it also changes the output (with "1"). But they
are different, just look at detailed description -

  - the T flip-flop changes the output (with "1") after **every rising
    edge on the input** (good to use button there - it generates rising
    edge of signal with every press).
  - the D latch changes the output (with "1") **due to the state on
    input**. Where there is "0", the first output will be also "0" and
    the second will be "1". Where there is "1" at the input, the first
    will be also "1" and the second will be "0"

Here are some pics for better understanding -

("Input" is the upper switch. The switch under it is clock input (it
does the same as all clock inputs))

Dlatch_tut.jpg|Input is ON, so the first output is ON, second is OFF
Dlatch_tut2.jpg|Input is OFF, so the first output is OFF, second is ON

[Category:Concepts](Category:Concepts "wikilink")
[Category:Electricity](Category:Electricity "wikilink") [Category:Tips
and Guides](Category:Tips_and_Guides "wikilink")
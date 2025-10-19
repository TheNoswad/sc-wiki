---
title: Multiplexers_and_Demultiplexers
description: 
published: true
date: 2025-10-13T00:04:04.673Z
tags: 
editor: markdown
dateCreated: 2025-10-13T00:04:00.568Z
---

Multiplexers (MUX) and Demultiplexers (DEMUX) are electrical circuits
that are used it many integrated circuits and so. They use an address
control line (usually analog) and control the flow of a data signal. The
MUX takes many inputs and has one output. The address line controls
which of the many inputs goes to the one output. The DEMux has one input
and many outputs. The address line controls which of the many outputs is
connected to the one input. In either case, only one of the many
inputs/outputs is connected to the one output/input.

### **Multiplexer**

Multiplexers have **many inputs** (this number differs for each), but
just **one output** (this number is still the same).

They allow you to control what input is "showing" on the output. Several
control signals or switches are used to create the address. The number
of address lines depends on the number of inputs (2in=1cs, 4in=2cs etc).
Each input has its own binary address which must be "entered" with the
control signals. An analog signal may be used for the address signal.

Note that analog data signals will pass properly through the basic logic
gates.

Let's try an example:

*You have several thermometers placed around your property and want to
check them now and again. You can use a mux (multiplexer) to be able to
read them each from just one place. Just set the switches to choose the
one you want to read. You can only see one at a time but you won't have
to run around to look at them.*

Now a pic of Multiplexer, also with labels -

![MUX.jpg](MUX.jpg "MUX.jpg")

### **Demultiplexer**

Demultiplexer (as you can guess, according to its name) does exactly the
opposite thing. DEMUX has only **one input** (still just one), but
**many outputs** (this number differs for each application).

It allows you to control which output will "follow" the state of the
input. Again, several control lines or switches are used to address the
specified output. The number of address lines depends on the number of
outputs (2out=1cs, 4out=2cs etc) or it could be an analog signal. Each
output has its own address in binary code which must be "entered" on the
control signals.

Here's an example of use:

*You have a stable with 8 stalls and have gates on each one. You want to
be able to open and close only one gate at a time. Use a demux to let
you set the door number and then just one door button.*

Here is a picture of Demultiplexer with labels - ![DEMUX.jpg](DEMUX.jpg
"DEMUX.jpg")

A demux circuit may not even include a data input depending on the
application. The proper output line may be set active as soon as the
address is established. An example is an electric 'sundial' clock face
which will always have one and only one point lit around the circle.

A much simplified demux may be made with [memory
banks](../Recipaedia/Electrics/Memory_Bank.md "wikilink"). One or both of the address inputs are
connected to the address line in the demux. Memory banks always have to
be programmed properly for their use. The simple demux only needs an 'F'
in proper address, which depends on the application.

If you need to pass an analog signal, that can go to the other address
input but the memory has to be programmed properly. Remember that analog
signals do not 'pass through' a memory. Or the demux output can go to an
[AND](../Recipaedia/Electrics/Logic_AND_Gate.md "wikilink") gate with the analog signal going to
the other input.

## **Download links**

Now you should understand how do MUX and DEMUX work. If you want to look
at them in detail or just rebuild them into your world, this [world
link](https://dl.dropboxusercontent.com/s/xri9wromuhc7w6a/deMUX.scworld?dl=1)
should help you.

*NOTE: I tried to write this guide in "normal language" (that means I
did not use too technical names and so). If you still can't understand,
or if you've found any mistakes, PM me [on the
wiki](http://survivalcraftgame.wikia.com/wiki/Special:EmailUser/JustPlaying)
or on forums - name is JustPlaying. I will try to correct all my
mistakes and make this guide better and easier to understand.*

[Category:Electricity](Category:Electricity "wikilink")
[Category:Circuits](Category:Circuits "wikilink")
[Category:Electricity](Category:Electricity "wikilink")
[Category:Circuits](Category:Circuits "wikilink")
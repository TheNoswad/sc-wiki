---
title: Advanced_Door_Control
description: 
published: true
date: 2025-10-12T23:29:49.874Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:29:45.940Z
---

This is a circuit designed to control a door. That might seem very
simple since all you really need are two buttons and some wires. But you
have to stop, turn around and hit a button to shut it behind you.

The next step up in complexity is to put a button on the outside and a
pressure plate on the inside. But you still have to stop to close the
door when you go out. If you also put a pressure plate on the outside
then beasts can open the door by stepping on it.

This circuit puts a button on both the inside and the outside. It also
has a pressure plate on both the inside and outside. When you approach
the door from either side, you press the button to open it. Then *after*
you pass through and over the *other* plate, the door will shut. The
trick is that when it's opened from the inside, only the outside plate
will close it and vice versa. Either way, either plate will only *close*
the door. If it's already closed, the plates do nothing. You cannot open
the door by stepping on either plate.

The circuit schematic is shown below. The light represents the door. The
holes just keep the wires from shorting to the switch or plate.

![Door_Control_Schem.jpg](Door_Control_Schem.jpg
"Door_Control_Schem.jpg")

The circuit has three parts. The first part has the two [SR
flipflops](SR_Latch "wikilink"). The button from one SR goes on the
INside while the plate from that SR goes on the OUTside, so they cross.
The opposite applies to the other SR. When you open the door from one
side, that SR puts a high on the output. You must pass through the door
and over the other plate to reset that SR.

The next stage is just the OR gate and this just combines the outputs
from the two SRs.

The third stage is an '[edge
detector](Clock_/_Pulse_circuits "wikilink")'. Doors in SurvivalCraft
only ''change ''when the signal goes high, so this circuit pulses the
door signal when the OR output *either* goes high or goes low. (If they
operated like in MC, this stage would not be needed.)

NOTE: The one problem with this (or any) door circuit is that the
circuit cannot tell if the door is open or closed. This is because they
are "edge-triggered" rather than "level dependant". (You don't need to
know what those terms mean yet.) This just means that you have to use an
Iron or Cell Door so that it cannot be opened by hand. It also means
that the door MUST be closed when the circuit is built (and both SRs
must be reset). The best way to do this is to place the door *after* the
circuit is complete and you have walked over both plates.

This circuit can also be used in other adventure world situations, with
or without the edge detector part. If you want something to be turned on
from different points but only turned back off from other points which
depend on where it was first turned on, this will work for you. As a
simpler example, say you want a time bomb started when someone walks
down a hallway. Then they have to find and press 2 buttons to stop it.
Put a pressure plate in that hall and run it to where both the buttons
go, in this circuit. Then hide the 2 buttons and connect one each to
where the plates are in this circuit. The OR output wil then control
your timer and you probably won't need the edge detector in this case.

This circuit will be included in my soon-to-be-released Circuits
Cookbook along with an actual application or two...

[Stanimus](User:Stanimus "wikilink")
([talk](User_talk:Stanimus "wikilink"))

[Category:Circuits](Category:Circuits "wikilink")
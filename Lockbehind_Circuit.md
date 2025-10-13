---
title: Lockbehind_Circuit
description: 
published: true
date: 2025-10-13T00:00:11.562Z
tags: 
editor: markdown
dateCreated: 2025-10-13T00:00:07.762Z
---

This page describes a circuit for controlling access through a door. The
circuit will lock the door after the character enters it the first time.
The door remains locked until the unlock switch is found and activated.

![Lockbehind_Circuit.png](Lockbehind_Circuit.png
"Lockbehind_Circuit.png")

This is the circuit diagram. The entry button will open or close the
door any time it is pressed. Once the character passes through the door
the pressure plate is activated and the door lock is engaged. Stepping
on the plate now will do nothing. This will also speak the sign that
tells the player that his character is trapped. It can be used to
release any 'caged' animals waiting for the character. Once the animals
are dispatched or avioded, the unlock switch must be found. This is
usually just a basic switch as shown, but could be a motion sensor wired
into a latch. The signal must stay ON for the circuit to stay unlocked.
If it's a simple switch, it could be hidden so the player must search
carefully. It could even be put in another location altogether. If you
don't want the character to ever exit through the same door, the switch
can simply be left out. In this circuit, the player is notified when the
unlock switch is activated, by another speaking sign.

Note that the OR gate has three inputs. There is no 3-in OR gate in SC.
But, any outputs that are wired together automatically forms an implict
OR between them. This means that the 3 inputs simply have to connect to
the door and to each other. No actual gate is needed. Only 5 actual
gates are used in the circuit. It can be built under the door for
concealment. With careful wiring, it can seem to be like any other
button controlled door from the outside. The unlock switch should be out
of sight from the door area and the wires should be hidden underground.
That way the player doesn't have any clue that this is a locking door.

This is a one-time circuit. Once it's activated, it can't be undone.
There's really no point to it once the player finds the unlock switch,
anyway. The Reset input on the SR can have a button installed to reset
it when you are testing the operation. 

An example of this circuit can be found in the [Circuit Cookbook world
by Stanimus](User_blog:Stanimus/Circuits_Cookbook "wikilink") . 

[Category:Circuits](Category:Circuits "wikilink")
[Category:Electricity](Category:Electricity "wikilink")
---
title: Random_Generator
description: 
published: true
date: 2025-10-13T00:08:24.175Z
tags: 
editor: markdown
dateCreated: 2025-10-13T00:08:20.227Z
---

__NOEDITSECTION__ __NOTOC__

A random generator outputs unpredictable values either at a variable
rate or synchronized to a clock input.

## Description   (From [Recipaedia](.. "wikilink") )

*Electric random generator. Can be used to generate random electric
signals. Has a single clock input and one random output. Output is an
analog signal and always indicates the latest result of the random
generator. Can work in synchronous or asynchronous mode, depending on
whether clock input is connected. In synchronous mode the random value
is generated only during a rising edge on the clock input, otherwise it
is generated continuously with average frequency of about 2 Hz. Can be
placed on any surface and rotated to desired orientation.*

## Crafting

it requires 4 [copper ingots](Copper_Ingot "wikilink") and 3 [germanium
crystals](Germanium_Crystals "wikilink") to craft Random
Generator.![Random_Generator_craft.png](Random_Generator_craft.png
"Random_Generator_craft.png")

You get 4 generator 'chips'.

## Operation

The Random Generator does not require any input. It will continuously
output a pseudo-random value and this value will change roughly twice
per second. If a clock signal is connected, it will only output a value
on the rising edge of this clock.

## Hooking it up

The output of the generator is at the 'top' of the chip. This is an
analog signal and must be fed to a device that accepts an analog signal.

The clock input (if used) is at the bottom of the chip and is a standard
digital signal that can be wired normally.

## Uses

A random generator is typically a specialized device. It can be used to
control lights for an interesting flashing look. It can be used in
adventures to create an unpredictable situation. It can be used in a
circuit that emulates the rolling of dice.

## History 

It was introduced in version 1.23.

[Category:Electricity](Category:Electricity "wikilink")
[Category:Electrics](Category:Electrics "wikilink")
[Category:Crafted](Category:Crafted "wikilink") [Category:Electric
Chip](Category:Electric_Chip "wikilink")
---
title: Photodiode
description: 
published: true
date: 2025-10-13T00:06:17.039Z
tags: 
editor: markdown
dateCreated: 2025-10-13T00:06:13.035Z
---

__NOEDITSECTION__

## Description (From [Recipaedia](Recipaedia "wikilink"))

*An electric photodiode. Used to detect light. The diode will set the
state of an electric circuit to 1 if there is enough light hitting its
surface. It has outputs on all sides for easy connection and can be
placed on any horizontal or vertical surface.*

## Crafting

Use 3 [copper ingots](Copper_Ingot "wikilink") and
one [glass](glass "wikilink") to craft photodiode. You get 2 diodes.
![Photodiode-0.png](Photodiode-0.png "Photodiode-0.png")

## Hooking it Up

Simply place the diode where you wish and run a single wire from any
side or back of the diode. Feed that wire to the rest of your circuit.

## Lighting values

The photoelectric diode reacts to the level of light around it and is
mostly used to detect environmental light from the [sun and
moon](Sun_and_Moon "wikilink"). The lighting values for various times of
day are as listed below. These levels were measured under a clear, open
sky without nearby structures blocking the sensor.

  - Full Day – 1.5V (F)
  - Dusk – 1.1V (B)
  - Sunset – 0.9V
  - Dark – 0.7V
  - Night – 0.5V
  - Midnight (new moon) – 0.0V
  - Dawn – 1.1 to 1.3V (B to D)

The dawn and dusk levels are lower when it’s a new moon that’s setting
or rising.

All this means that if you use the diode to turn lights on at dark, you
should not use the simple [NOT gate](Logic_NOT_Gate "wikilink"). Since
version 1.29, the [lightbulb](lightbulb "wikilink") takes analog input
signals and will not turn fully on, except on the darkest of nights. The
lightbulb page has a circuit that may be used as an interface or
controller, to allow it to be on full once the light gets below a
certain level. You can use the values listed below to program the
controller when to turn the lights on fully. The string used to program
the memory bank is included to make it easier.

  - If you want the lights to come on only once it’s dark, turn them on
    below 0.7V : FFFFFFF000000000
  - To turn them on at dusk, set it to under 0.8V: FFFFFFFF00000000
  - To turn them on when it starts to get dark, set it to under 1.2V:
    FFFFFFFFFFFF0000
  - You can also have the lights turn on gradually as it gets darker so
    they come on as the light first diminishes and are fully on once
    it’s completely dark. Use: FFFFFFFEDCBA9800

If your diode must be placed where it’s a little darker than in the
open, you just insert another ‘F’ at the beginning of the line. This
will make the light come on when it’s a little brighter. If there’s a
bit of artificial light on the sensor, delete an ‘F’ from the beginning
of the line and this will make them stay off until it’s a little darker.
Just remember the sensor still must be isolated from the light of
whatever it’s controlling, or it may go into feedback and oscillate
on/off/on/off…

See the [lightbulb](lightbulb "wikilink") page for the simple controller
circuit and the [memory bank page](Memory_Bank "wikilink") for
programming the bank.

## Adventure map uses

  - You may have a falling wall that opens up an area. It may be
    difficult to detect when this wall is triggered. If the character
    side of the wall is lighted, you could place a photodiode on the
    dark side of the wall and it will trigger once the wall is gone.

<!-- end list -->

  - If you have a long hallway, you could have the lights come on in
    sequence for effect. The first light comes on from a switch or other
    trigger. The next light is triggered by a photodiode that sees the
    light from the first light and turns the next group on. And so on.
    This setup doesn’t use the NOT type circuit. Instead it is directly
    connected to the lights, or through a ‘controller circuit’ that does
    not invert the signal. This type of circuit is not susceptible to
    the oscillating feedback. Instead, if there is feedback, the lights
    won’t turn off due to the sensor.

<!-- end list -->

  - Another use in adventure maps is setting photodiodes next to major
    explosives, so if light floods from player breaking it or otherwise,
    the explosive fuse is lit.

[Category:Electrics](Category:Electrics "wikilink")
[Category:Crafted](Category:Crafted "wikilink")
[Category:Electricity](Category:Electricity "wikilink")
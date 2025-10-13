---
title: 4-LED
description: 
published: true
date: 2025-10-12T23:29:04.866Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:29:00.948Z
---

__NOTOC__ __NOEDITSECTION__

## Description   (From [Recipaedia](Recipaedia "wikilink"))

*A set of 4 square light emitting diodes. When connected to a power
source, LEDs emit weak colored light. The element splits the analog
signal into 4 bits to determine which of the 4 diodes should be lit. The
light is too weak to light up the surroundings, but it's easily visible.
Useful for creating high resolution screens. It has inputs on all sides
for easy connection and can be placed on any horizontal or vertical
surface.*

## Crafting

To craft 4-LEDs, you need 3 [glass](glass "wikilink"), 3 [copper
ingots](Copper_Ingot "wikilink") and a [bucket of
paint](Paint_Bucket "wikilink") for color. They only use the reduced
color set. See the [painting page](Painting "wikilink").

<div style="overflow: hidden">

![4-led_craft.jpg](4-led_craft.jpg "4-led_craft.jpg")

</div>

## Hooking It Up

This is meant to be driven by an analog signal. The signal can be
connected on any side or the back. If it is connnected to a digital
signal, all the LEDs will turn on or off with the signal.

Each of the separate LEDs correspond to one of the 4 digital bits in the
'analog' signal. When placed vertically, the top left LED mirrors the A0
bit (least significant) and the bottom right mirrors the A3 bit (most
significant). When placed horizontally, the A3 LED is the N/E LED and
the A0 LED is the S/W LED. The charts show this graphically. They will
always be in this orientation no matter how you place them.

` Vertical:                    Horizontal:`
`    UP                           WEST`

`|—––—–—––—|                   |—––—–—––—|`
`| A0 | A1 |                   | A0 | A1 |`
`|—––—|—––—|                   |—––—|—––—|  NORTH`
`| A2 | A3 |                   | A2 | A3 |`
`|—––—–—––—|                   |—––—–—––—|`

## Uses

  - Often used in simulated televisions.
  - They can be used as animations in-game, like arcade machines and
    movies.
  - Use them as a compact way to monitor 4 different signals.

## History

  - 4-LEDs were added in 1.23.
  - 1.29 they can now be 8 colors

[Category:Electrics](Category:Electrics "wikilink")
[Category:Crafted](Category:Crafted "wikilink")
[Category:Electricity](Category:Electricity "wikilink")
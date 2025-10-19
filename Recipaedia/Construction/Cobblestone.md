---
title: Cobblestone
description: 
published: true
date: 2025-10-12T23:39:00.981Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:38:57.009Z
---

 __NOEDITSECTION__ __NOTOC__

## Description (From [Recipaedia](.. "wikilink"))

*Cobblestone is a tough stone obtained by mining granite. It is a
strong, rugged material that works well when used in construction of
walls and floors. By smelting it in a furnace you can obtain pure
granite of which it is made.*

Cobblestone is obtained when you break natural granite. 

## Automatic Stone Generator

With the introduction of pistons in V2.0, we can now make an infinite,
automatic cobblestone generator. It requires a single [Pulling
Piston](../Electrics/Pulling_Piston.md "wikilink"), a [Chest](Chest "wikilink"), a
bucket each of water and magma, and a handful of fire-proof blocks for
the mechanical part. For the electric part, you'll need a [toggle
switch](Switch "wikilink"), some [wires](../Electrics/Electric_Wire.md "wikilink"), a
NAND gate and an [Adjustable Delay
Gate](../Electrics/Adjustable_Delay_Gate.md "wikilink").

Set the delay to the minimum (0.01Sec). Set the piston to Max=1,
Blocks=1 and Speed=Slow.

<div style="overflow:hidden">

![Cobble_Gen.jpg](Cobble_Gen.jpg "Cobble_Gen.jpg")

</div>

In this image, the chest is placed under the water, below where the
splash mark is. This will catch all [debrised](Debris "wikilink")
(broken) blocks as noted below.

-----

You must note that Survivalcraft throws the debrised block in certain
directions only\! Specifically to the east and south. This is important
because you need to modify the design according to the direction it's
facing. The above layout is valid only when facing the west or north.
That means the NAND gate faces the stated direction.

If the machine cannot face either west or north, then it will throw
debris where the chest does not collect it. So, one more chest is
required to catch all thrown blocks. Also, the water and magma have to
be swapped. See the image below.

<div style="overflow:hidden">

![Cobble_Gen_B.jpg](Cobble_Gen_B.jpg "Cobble_Gen_B.jpg")

</div>

<div style="overflow:hidden">

![Cobble_Gen_position.jpg](Cobble_Gen_position.jpg
"Cobble_Gen_position.jpg")

</div>

Sometimes this machine will start producing basalt instead of
cobblestone. When it does you may have to quit the world and start it up
again. It should work fine after then. (This is a GLITCH machine, after
all.)

## Uses

  - Cobblestone can be smelted in a [furnace](furnace "wikilink") to
    make [granite](granite "wikilink").
  - It may be used to make [stairs](Stone_Stairs "wikilink") and
    [slabs](Stone_Slab "wikilink").
  - It is used to make stone [tools](:Category:Tools "wikilink") and
    [weapons](:Category:Weapons "wikilink").
  - Can be painted.
  - When painted granite is destroyed it will drop painted cobblestone

## History

Added in 1.0

[Category:Blocks](Category:Blocks "wikilink")
[Category:Terrain](Category:Terrain "wikilink")
[Category:Natural](Category:Natural "wikilink")
[Category:Construction](Category:Construction "wikilink")
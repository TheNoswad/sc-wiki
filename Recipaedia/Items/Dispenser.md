---
title: Dispenser
description: 
published: true
date: 2025-10-12T23:46:22.489Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:46:18.361Z
---

__NOTOC__ __NOEDITSECTION__

## Description (from Recipaedia)

*A dispenser stores items in a similar way to a chest, but allows
dispensing them through the hole when triggered via a rising edge of an
electric signal. It can either dispense the item or shoot it as a
projectile, depending on the setting.*

<div style="overflow: hidden">

![Dispenser](Dispenser.md "Dispenser")

</div>

## Crafting

Requires 7 [planks](planks "wikilink"), one [bow](bow "wikilink") and
one [germanium crystal](germanium_Crystal "wikilink") to craft one
dispenser.

<div style="overflow: hidden">

![1450544272475.png](1450544272475.png "1450544272475.png")

</div>

## Use

<div style="overflow: hidden">

![Dispenser_interface-0.jpg](Dispenser_interface-0.jpg
"Dispenser_interface-0.jpg")

</div>

Place the dispenser in the direction you wish it to shoot. The face with
the hole in it is where the items will be shot from. When it is placed,
the hole will always face the player.

To configure the dispenser, simply approach it and 'tap' it. A window
will pop up to show the dispenser's inventory, two buttons and an
"accept drops" option. It also shows your inventory.

Place the items you wish to dispense/shoot in the dispenser slots (8
total). Select one button whether you want it to dispense or shoot the
items (dispense is the default setting). With "dispense" items are
simply dropped and can be collected much like any drop, with "shoot"
items are fired as projectiles at the direction where dispenser is
faced.

As of version 2.1, if "accept drops" is enabled, dispensers will collect
items thrown or dropped onto them much like chests.

## Controlling it

Connect the dispenser to your electric circuit. This could be as simple
as a [button](button "wikilink") placed directly next to it. When the
circuit is charged (rising edge), the dispenser will dispense/shoot.

[Switches](../Electrics/Switch.md "wikilink") are a very inefficient way to activate
dispensers, requiring two 'taps' to fire. Buttons are preferable.

A useful control circuit involves a few [electric
wires](../Electrics/Electric_Wire.md "wikilink"), a [NAND](../Electrics/Logic_NAND_Gate.md "wikilink")
(or [XOR](../Electrics/Logic_XOR_Gate.md "wikilink")) gate and a
[switch](switch "wikilink"). One input of the NAND is connected to the
output. This creates a high-frequency oscillator. The other input is
connected to the switch. The NAND output is connected to the dispenser.
When the switch is on, the dispenser will fire extremely quickly (max.
3000 rpm), like a machine gun. When firing gunpowder kegs the lag
created can massively decrease firing rate.

## Notes

![Trap_with_a_durable_bait.jpg](Trap_with_a_durable_bait.jpg
"Trap_with_a_durable_bait.jpg")

  - Can shoot/dispense in any direction it has been placed.
  - Any block or item may be dispensed from it.
    [Bombs](../Weapons/Bomb.md "wikilink"), [Incendiary
    Bombs](../Weapons/Incendiary_Bomb.md "wikilink"), [Gunpowder
    Kegs](Gunpowder_Kegs.md "wikilink"), [Incendiary
    Kegs](Incendiary_Kegs "wikilink") and
    [Fireworks](Firework "wikilink") will be ignited as they leave the
    dispenser. So are [fire arrows](fire_Arrow "wikilink") and
    [explosive bolts](explosive_Bolt "wikilink").
  - [Spawner eggs](Eggs "wikilink") (NOT laid eggs) may be dispensed.
    They will immediately hatch.
  - Great for defending houses, bases, etc without endangering the
    character.
  - Can be used to drop items used as bait for animal traps. If you
    build a trap with the returning of an item, the animals will not be
    able to eat the bait before it returns to the dispenser.
  - The electric connection can be made through a
    [wire](../Electrics/Electric_Wire.md "wikilink") or a
    [wire-through-block](../Electrics/Wire_Through_Bricks.md "wikilink") may be placed
    against any surface for connection.
  - All [ammunition](weapons "wikilink") shot from the dispenser will
    pass through a single-block opening directly in line with the
    dispenser if that opening is no more than 6 blocks from the face of
    the dispenser (5 block passage). This can be used in adventure maps
    to provide a 'kill zone' but prevent the character from retrieving
    any shot ammo. You will have to ensure that no ammo will bounce back
    through the opening, however. One great way to do this is to have a
    wall of clay behind that opening. Projectiles always stick to clay\!
  - If [Buckshot](../Weapons/Buckshot.md "wikilink") is fired by the Dispenser, it
    doesn't cause any damage. It only knockbacks
    [Entities](Entities "wikilink").
  - You can use seemingly useless items (Such as dirt blocks, unripe
    pumpkins, etc) to use as Dispenser ammo. Good for protecting your
    home\!
  - You cannot edit a dispenser in [Adventure
    Mode](Adventure_Gamemode "wikilink").

## History

1.28. Added Dispenser.

1.29. Dispensers are no longer editable in adventure mode.\[1\]

## References

<references />

[Category:Blocks](Category:Blocks "wikilink")
[Category:Crafted](Category:Crafted "wikilink") [Category:Dangerous
items](Category:Dangerous_items "wikilink")
[Category:Electricity](Category:Electricity "wikilink")
[Category:Items](Category:Items "wikilink")

1.  <https://kaalus.wordpress.com/updates-history/>
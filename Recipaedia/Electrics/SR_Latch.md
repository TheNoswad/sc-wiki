---
title: SR_Latch
description: 
published: true
date: 2025-10-13T00:11:19.049Z
tags: 
editor: markdown
dateCreated: 2025-10-13T00:11:15.006Z
---

__NOEDITSECTION__

## Description   (from [Recipaedia](.. "wikilink"))

*Logic SR latch. Can be used as a memory element holding a single bit.
Has three inputs (S, R, and clock), and one output. A signal on S input
sets the state to 1. A signal on R input resets the state to 0. Output
always indicates the current state of the latch. Can work in synchronous
or asynchronous mode, depending on whether clock input is connected. In
synchronous mode the states of S and R inputs are read only during a
rising esge on the clock input. Can be placed on any surface and rotated
to desired orientation.*

## Crafting

Crafting requires 5 [Germanium
Crystals](Germanium_Crystals "wikilink") and 2 [Copper
Ingots](Copper_Ingot "wikilink"). You get 4 latches.

![SR_latch_craft.png](SR_latch_craft.png "SR_latch_craft.png")

## Hooking It Up

### Modes

SR Latch has two modes, asynchronous (clock is not connected) and
synchronous (clock is connected).

  - *Asynchronous mode*

<!-- end list -->

  -
    *​*The Latch outputs a 1 when the SET input changes to 1. It will
    stay at 1 even when the S input returns to 0. The output will only
    return to 0 when Reset changes to 1 AND the Set is at 0.

<!-- end list -->

  - *Synchronous mode*

<!-- end list -->

  -
    This latch is considered dominant Set. That means that if both S and
    R inputs are active, the Set will override the Reset and the latch
    will NOT reset until the Set returns to 0.
    The Latch will only change its output when the clock input changes
    to 1. Then the output will be 1 if Set is 1. It will only be 0 if
    Reset is 1 AND Set is 0.

### Connections

The output is at the 'top' - the single dot without a letter by it. The
S and R inputs are where the letters are. The clock input is where the
arrow or dart is (the 'bottom'). All signals are digital.

### **Truth Table**

<span style="font-size:13px;line-height:21px;">Truth table shows all
input combinations and the output signal for each combination.</span>

| Input | Output |
| ----- | ------ |
| S     | R      |
| 0     | 0      |
| 1     | 0      |
| 1     | 1      |
| 0     | 1      |

See modes above, for the difference between sync and async modes. The
table is no different for either mode.

## Uses

  - It is used where you want to turn something on at one place but turn
    it off from another place.
  - The latch can be used to simulate a lever switch when only a button
    can be used. It needs a little extra circuitry (to make it a T
    latch).
  - It will remember if you turned something on.
  - It is mostly used in bigger circuits and is very flexible and useful
    device.
  - It can be used to extend the range of an electric signal, beyond the
    view distance limit. 

[Category:Electricity](Category:Electricity "wikilink")
[Category:Electrics](Category:Electrics "wikilink") [Category:Electric
Chip](Category:Electric_Chip "wikilink")
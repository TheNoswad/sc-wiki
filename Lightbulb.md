---
title: Lightbulb
description: 
published: true
date: 2025-10-12T23:59:43.066Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:59:38.954Z
---

__NOEDITSECTION__ __NOTOC__

## Description (From [Recipaedia](Recipaedia "wikilink"))

*Electric lightbulb, emits a lot of light when connected to a source of
electricity. Can be placed on any vertical or horizontal surface.*

Beginning with V2.0 lightbulb frames may be painted any of the 16 paint
colors.

## Crafting

Crafting requires 4 [copper ingots](copper_Ingot "wikilink") and one
[glass](glass "wikilink"). You get 8 lightbulbs.
![Lightbulb-0.png](Lightbulb-0.png "Lightbulb-0.png")

## Controlling it

  - As of version 1.29, the lightbulb is an analog device. This means
    that it will respond to the voltage value at the input. Any voltage
    of 0.8 or higher will turn it on but the brightness will depend on
    that voltage. A voltage of 0.8 will light it dimly while the value
    of 'F' (voltage 1.5) will light it fully. This can cause some
    problems with previous circuits - especially when it's driven by a
    simple photodiode and NOT gate. Both the diode and gate use analog
    signals and so, may not light the bulb fully.
  - One way to get around this issue is to use a "Lightbulb Controller"
    before any bulb or string of them. This controller can supply a
    maximum signal to the bulb for all values of the input, from 0.8 to
    1.5 volts which makes the bulb respond as a straight digital device
    again.
  - This controller is a simple Memory Bank. The signal that would feed
    the lightbulb is routed to the LOW address of the Bank and the
    output of the Bank is then fed to the bulb. This makes for a simple
    connection.
  - The Bank is programmed to respond to the signal in a digital manner
    by using the following data: 00000000FFFFFFFF This can be typed in
    (it's 8 '0' then 8 'F') or copied and pasted into the edit box, in
    line 0.
  - You can also use other data to make the lightbulb react differently
    and may even use the bank to provide additional logic processing.
    See the [Memory Bank](Memory_Bank "wikilink") page for more info.
    For instance, instead of putting 'F's, you could put lower numbers
    such as 'C'. This will still turn the lights on but make them
    dimmer, for some 'mood lighting'.

### Simple Controller

  - You can use this controller with a simple
    [photodiode](photodiode "wikilink") to turn the lights on at night
    without the need of a NOT gate. Connect it the same way as described
    above but program it with 'inverted' data: FFFFFFFF00000000 If you
    put more (than 8) 'F's, the lights will come on before it gets
    completely dark. This can avoid some problems, such as light from
    other sources getting to the diode. Using FFFFFFFFFFFFFFF0 will turn
    the lights on any time the sun is not shining directly on the
    photodiode.

<!-- end list -->

  - If you cannot use the LOW address input and have to use the HIGH
    address input, then the same data must be programmed but, instead of
    it being in the '0' ROW, it must run down the '0' COLUMN. See the
    [Memory Bank](Memory_Bank "wikilink") page for help.

## History

  - 1.19: Added Lightbulbs.
  - 1.21: Increased Lightbulbs size.
  - 1.29: Light intensity now can be analogically controlled.
  - 2.00: They are paintable and gained a new texture (now uses glass
    and copper ingot textures instead of a proprer one).

## Notes

  - If a projectile hits a lightbulb, it will shatter.
  - To see more information on the light levels for each time of day and
    more detailed programs for the controller, see the [photodiode
    page.](Photodiode#Lighting_values "wikilink")
  - Lightbulb can be powered from any side or the back (with a wire
    through block).
  - It will brightly light up an area about 6 blocks from the bulb
    (placed on the ground). The light diminishes farther away and is
    useful to about 12 blocks.
  - They can be seen from a long distance.
  - They are very inexpensive to craft.
  - Click for more information on [analog
    signals](Using_Analog_Signals "wikilink")

[Category:Electricity](Category:Electricity "wikilink")
[Category:Electrics](Category:Electrics "wikilink")
[Category:Crafted](Category:Crafted "wikilink")
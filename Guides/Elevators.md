---
title: Elevators
description: 
published: true
date: 2025-10-12T23:47:35.198Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:47:31.231Z
---

Elevators are used to avoid building long staircases.

NOTE that since V2.0, elevators are much simpler to build [using
pistons.](Piston_Lifts.md "wikilink")

## Watervator

They can be made several different ways. The simplest is to use a column
of water. However, since version 1.26, you can freeze to death from
being wet. Also, if you are wearing armor, you will not float upwards
and will instead, drown. 

<div style="overflow:hidden">

Elevator_water_tut3.jpg|Make it higher Elevator water tut2.jpg|Make it
higher Elevator_water_tut4.jpg|Make it higher

</div>

## Compact Electric Elevators

Several electric based elevator designs are possible. Typically a design
can only move the character either up or down. To make a single elevator
that can move up and down would be more complex and will be covered
later. 

Electric elevators use trap doors to push the character up one block
level. After a short delay, the trap door on the next layer closes and
pushes the character up one more layer, etc. 

A down elevator works similarly but instead of pushing the character up,
it allows the character to fall only a short distance at a time. 

The following images depict a compact design. The actual shaft is a 2x2
space rather than the minimum 1x1. This avoids some problems inherent in
the 1x1 designs. 

The electrics are very simple. For the UP elevator, you only need one
delay gate between each layer. For the down elevator, simply add one
more delay gate between every other layer.

<div style="overflow:hidden">

![New_Elevator_front.jpg](New_Elevator_front.jpg
"New_Elevator_front.jpg")

![New_Elevator_side1.jpg](New_Elevator_side1.jpg
"New_Elevator_side1.jpg")

![New_Elevator_top.jpg](New_Elevator_top.jpg "New_Elevator_top.jpg")

</div>

The design only requires one delay gate and some wires for each level,
for the up elevator. Of course you will need 4 trap doors and some
blocks as well. The down elevator requires one more delay gate for every
other level, to slow down your descent. 

As of ver.1.29, we have variable delay gates. Instead of using 2 delays
to slow dowwn the drop elevator, we can use a single adjustable delay
set to a longer wait.

The complete design is difficult to describe and show in pictures. You
can download a world that shows you how to build it,
[HERE](https://dl.dropbox.com/s/xn672ecmsbhudpk/Elevators.scworld?dl=1).
A completed pair is also included in the [Circuit Cookbook world by
Stanimus](User_blog:Stanimus/Circuits_Cookbook "wikilink"). 

## Up and Down

A single elevator that can go both up OR down is a simple combination of
the two circuits. Both the up and down circuits are simply delay chains.
You can combine them (at every flap) with an OR gate.

This is easy in theory and the only 'hard' part is fitting the physical
layout within the space required. Remember we would need 2 delays, the
OR, and all connections to fit within a single block height.

## Notes

  - Survivalcraft can only handle a certain amount of electric devices
    in a small area. A very tall elevator (100 blocks+) will push this
    near the limit. If you want an up elevator near a down elevator, you
    may have to space them out (not in the same chunks) to avoid
    glitching the game. 
  - This is a basic design. It will only take you from one floor to the
    next. It does NOT have a 'floor selector' control. There are much
    more complicated designs which do have a floor chooser circuit and
    one may be added to this page in the future.

[Category:Tips and Guides](Category:Tips_and_Guides "wikilink")
[Category:Crafted](Category:Crafted "wikilink")
[Category:Concepts](Category:Concepts "wikilink")
[Category:Circuits](Category:Circuits "wikilink")
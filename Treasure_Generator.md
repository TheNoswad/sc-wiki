---
title: Treasure_Generator
description: 
published: true
date: 2025-10-13T00:21:45.714Z
tags: 
editor: markdown
dateCreated: 2025-10-13T00:21:41.683Z
---

## Description

Treasure Generator is a transparent block that has the characteristics
of air, but has a shadow.

It can not be placed manually. To place it, you need to either replace
the ID of the block that makes up the flat world (in "Project.xml"
file), or replace the ID of the moving block (in "Project.xml" file), or
edit the .dat file with chunks. Two such blocks are generated under the
graves.

## Behavior

The Treasure Generator does not respond to any interaction except
breaking any of the six adjacent blocks (including retracting pistons)
or replacing them with water. In this case, it will turn into air. At
the same time, items will appear in its place with a probability of
0.25: 3 to 6 Experience Orbs and treasure. The treasure is randomly
selected from the following list and can drop in an amount from 1 to
'MaxCount':

| Item                  | Probability         | MaxCount |
| --------------------- | ------------------- | -------- |
| Stone Chunk           | 0.0344827586206897  | 4        |
| Diamond               | 0.00862068965517241 | 1        |
| Malachite Chunk       | 0.0344827586206897  | 4        |
| Iron Ingot            | 0.0172413793103448  | 3        |
| Copper Ingot          | 0.0344827586206897  | 3        |
| Coal Chunk            | 0.0344827586206897  | 4        |
| Sulphur Chunk         | 0.0172413793103448  | 4        |
| Solid Coal Block      | 0.00862068965517241 | 1        |
| Planks                | 0.0172413793103448  | 16       |
| Leather               | 0.0172413793103448  | 4        |
| Fur                   | 0.0172413793103448  | 4        |
| Wicker Lamp           | 0.0172413793103448  | 2        |
| Torch                 | 0.0344827586206897  | 4        |
| Match                 | 0.0344827586206897  | 8        |
| Gunpowder             | 0.0172413793103448  | 4        |
| Small Gunpowder Keg   | 0.00862068965517241 | 4        |
| Medium Gunpowder Keg  | 0.00862068965517241 | 2        |
| Large Gunpowder Keg   | 0.00862068965517241 | 1        |
| Small Incendiary Keg  | 0.00862068965517241 | 4        |
| Medium Incendiary Keg | 0.00862068965517241 | 2        |
| Large Incendiary Keg  | 0.00862068965517241 | 1        |
| Jack O'Lantern        | 0.0172413793103448  | 2        |
| Rye Seeds             | 0.0689655172413793  | 8        |
| Cotton Seeds          | 0.0344827586206897  | 8        |
| Pumpkin Seeds         | 0.0689655172413793  | 8        |
| Oak Sapling           | 0.0172413793103448  | 8        |
| Birch Sapling         | 0.0172413793103448  | 8        |
| Spruce Sapling        | 0.0172413793103448  | 8        |
| Tall Spruce Sapling   | 0.0172413793103448  | 8        |
| Mimosa Sapling        | 0.0172413793103448  | 8        |
| Bow                   | 0.0344827586206897  | 1        |
| Copper Tip Arrow      | 0.0172413793103448  | 2        |
| Iron Tip Arrow        | 0.0172413793103448  | 2        |
| Diamond Tip Arrow     | 0.00862068965517241 | 2        |
| Fire Arrow            | 0.0172413793103448  | 2        |
| Crossbow              | 0.00862068965517241 | 1        |
| Iron Bolt             | 0.0172413793103448  | 2        |
| Diamond Tip Iron Bolt | 0.00862068965517241 | 2        |
| Explosive Bolt        | 0.00862068965517241 | 2        |
| Musket                | 0.00862068965517241 | 1        |
| Iron Machete          | 0.00862068965517241 | 1        |
| Diamond Edge Machete  | 0.00862068965517241 | 1        |
| Iron Spear            | 0.00862068965517241 | 1        |
| Diamond Tip Spear     | 0.00862068965517241 | 1        |
| Iron Shovel           | 0.00862068965517241 | 1        |
| Diamond Edge Shovel   | 0.00862068965517241 | 1        |
| Iron Pickaxe          | 0.00862068965517241 | 1        |
| Diamond Tip Pickaxe   | 0.00862068965517241 | 1        |
| Iron Axe              | 0.00862068965517241 | 1        |
| Diamond Edge Axe      | 0.00862068965517241 | 1        |
| Iron Rake             | 0.00862068965517241 | 1        |
| Diamond Spikes Rake   | 0.00862068965517241 | 1        |
| Bucket                | 0.00862068965517241 | 1        |
| Whistle               | 0.00862068965517241 | 1        |
| Saddle                | 0.0172413793103448  | 1        |
| Electric Wire         | 0.00862068965517241 | 10       |
| Motion Detector       | 0.00862068965517241 | 2        |
| Button                | 0.00862068965517241 | 2        |
| Switch                | 0.00862068965517241 | 2        |
| Piston                | 0.00862068965517241 | 2        |
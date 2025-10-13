---
title: Coordinates
description: 
published: true
date: 2025-10-12T23:40:30.060Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:40:26.039Z
---

## Description

If you are in creative mode and you pause the game, the current location
of the character is displayed as coordinates in the information section
at the top of the pause screen (Location: x, z at altitude y). This can
be used to remember specific location(s) when building large structures
or scattered objects.

| Dimension | Direction          | When increasing       |
| --------- | ------------------ | --------------------- |
| x         | East-west          | As you move westward  |
| y         | Up-down (altitude) | As you move higher    |
| z         | North-south        | As you move northward |

## Altitude

Some features are dependent on the altitude. The altitude of a block is
defined by where the *bottom* of that block is placed. When you stand on
a block, the altitude displayed is the level where your *feet* are.
Thus, when you stand on the shore of the ocean, the display shows
altitude of 65. This means the *bottom of the top block* of water in the
ocean is at altitude 64.

| Altitude | Features                                                                                                                                                                                                           |
| -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| \< 0     | The 'void'. Due to an invisible [bedrock](bedrock "wikilink") above you can see caves and lava lakes. You die. You can get into this void only by [hacking the Project file](Hacking_the_Project_file "wikilink"). |
| 0        | Bedrock begins at this level and can be several blocks thick. The first layer (at level 0) is invisible bedrock.                                                                                                   |
| 2        | Minimum level of flat terrain generation.                                                                                                                                                                          |
| 2–40     | Above the bedrock layer, the [basalt](basalt "wikilink") layer begins, with the ores associated with it. This continues up and through part of the [granite](granite "wikilink") levels.                           |
| 20–40    | Transition between the basalt and granite layers. Granite and its ores are prevalent above here and can extend to the highest mountains.                                                                           |
| 64       | Sea level, typical minimum land level.                                                                                                                                                                             |
| 252      | Maximum level of flat terrain generation.                                                                                                                                                                          |
| 254      | Maximum buildable level. You can extend one piston's block above this level but it will be invisible (like at the '0' level).                                                                                      |
| 296+     | You die.                                                                                                                                                                                                           |
| 600      | Cloud level.                                                                                                                                                                                                       |

Note that although the basalt levels are primarily 2 through 32 and
granite above that, granite can be found at the very bottom and basalt
can occasionally be found near the tops of mountains. These levels
stated are not strict but are general guidelines.

## History 

  - 1.26- Added the coordinates display.
  - 1.27- Cloud level and death height were increased.
  - 2.1- The drop-off point is close to 0, 65, 0.
  - 2.2- Terrain height was doubled to 256 blocks, therefore cloud level
    and death height were again increased.

[Category:Help Pages](Category:Help_Pages "wikilink") [Category:Tips and
Guides](Category:Tips_and_Guides "wikilink")
[Category:Concepts](Category:Concepts "wikilink")
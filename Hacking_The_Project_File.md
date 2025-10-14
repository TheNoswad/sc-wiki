---
title: Hacking_The_Project_File
description: 
published: true
date: 2025-10-12T23:53:11.010Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:53:03.730Z
---

The project.xml file is created by the game and holds all the data for
the world that is not included as terrain. It is in xml format and can
be read and modified using many different tools, such as a text editor.

This file holds data specific to the world, not to the game itself. For
instance, it holds the design of any furnitures used in the world. Any
other furniture imported into the game's "content" but not added in the
world will NOT be included in the project file.

The actual .xml file has a lot of 'formatting' needed for the computer
to read it. All that 'extra' formatting has been removed in the samples
shown in this article.

## Opening the world file

To edit the project.xml file, you need to be able to do 3 things.

First you must be able to locate the world file. This is the
worldname.scworld file that the world is saved as. It is just a 'zip'
collection of several files the game creates for the world. This is
found inside the folder Survivalcraft makes for itself.

Second you must be able to extract the project file from inside the
world file, and then replace the file with the modified version. Many
file browsers let you extract the file without 'unzipping' the entire
.scworld file.

Third you have to be able to edit the project file. This only requires a
basic text editor. A basic editor may be better than a full-featured one
because the file MUST be saved as a text-only file. It cannot be in rtf,
doc, or any other format.


\===Opening it in Android===

If you are android user, you can easily edit the project.xml with your
device. There are several apps that will be helpful. The first is a file
browser that lets you open zip files. A good one is X-Plore and another
is called File Manager made by Cheetah Mobile.

1.  Upload the world that you want to edit to sd card.
2.  Open the file browser and find the folder named "Survivalcraft", in
    the internal memory. It's usually at the top of the file tree.
3.  Open the folder. There will be the list of all worlds you had
    uploaded to SD.
4.  Select the file you just saved (the most recent one) then change the
    extention to ".zip".
5.  Open the zip file (You can open it without unzipping it if you use
    the recommended apps). You will see at least three files:
    chunks.dat, project.bak, project.xml. Chunks.dat contains the data
    about chunks (duh). The project.bak file is a backup for the
    project.xml file.
6.  EDIT THE "project.xml" FILE.
    1.  You should copy this file to another location while editing it.
    2.  Use a text editor to make the changes. Be sure to resave it in
        plain text format.
    3.  When finished, copy the file back into the original 'zip' file.
7.  Change the world file's extention back to ".scworld".

### Opening it in windows

Opening it in a desktop or mobile windows machine is very similar to
using android. The process is the same, only the location of the world
files are different.

Two users report that this is the common location for the world files:
%USERNAME%\\AppData\\Local\\Packages\\20961CandyRufusGames.Survivalcraft2_(some
letters and/or numerals)\\LocalState\\Worlds\\World(number or nothing,
if it's the first world).

### Opening it in iOS

Apple users have a different 'problem'. iOS does not allow you to save
to SD memory, so the world has to be uploaded to dropbox first.

Then you must access the world as a zip file. This may be easiest by
using another system. At this point, the procedure is the same.

Once you're finished editing it and changed the extention back to
".scworld", it must be resaved to dropbox so Survivalcraft can access it
again.


\==Project file description==

The file is arranged into two main sections with sub-sections inside
them.

### Subsystems

This holds most of the useful information.

Inside of "Subsystems" are the following entries. Some may not be
present in your world and they may have different orders. Some sections
may be very large if you have a lot of that particular item in your
world.

  - "PlayerStats"
  - "Players"
  - "TruthTableCircuitrBlockBehavior"
  - "Spawn" (which may be HUGE)
  - "Pickables"
  - "MemoryBankBlockBehavior"
  - "ExplosivesBlockBehavior"
  - "WoodBlockBehavior"
  - "Camera"
  - "Weather"
  - "SignBlockBehavior"
  - "Projectiles"
  - "MovingBlocks"
  - "GameInfo"
  - "FurnitureBlockBehavior"
  - "Intro"
  - "Electricity"
  - "Gui"
  - "SaplingBlockBehavior"
  - "BlocksScanner"
  - "RotBlockBehavior"
  - "MagnetBlockBehavior"
  - "TimeOfDay"
  - "CollapsingBlockBehavior".

### Entities

This section can be huge. It holds the individual information for each
entity - that is each player, chest, crafting table, furnace, dispenser
and every 'active' animal. These are not in any specific order but the
parts for players will generally be first in this section.

The first line for each entity has a unique identifying number (GUID)
and the name of the type of entity. The next lines depend on what that
entry is. Some may be short and some are long.

## Individual Entry Descriptions

### Game Info

This is a sample (stripped down) Game Info entry:

    ﻿   "WorldName" = "Phoenix Federation" /
       "OriginalSerializationVersion" = "2.0" /
       "GameMode" = "Cruel" /
       "EnvironmentBehaviorMode" = "Living" /
       "TimeOfDayMode" = "Changing" /
       "AreWeatherEffectsEnabled" = "True" /
       "IsAdventureRespawnAllowed" = "True" /
       "AreAdventureSurvivalMechanicsEnabled" = "True" /
       "AreSupernaturalCreaturesEnabled" = "False" /
       "WorldSeedString" = "" /
       "TerrainGenerationMode" = "Continent" /
       "IslandSize" = "200,200" /
       "TerrainLevel" = "64" /
       "TerrainBlockIndex" = "8" /
       "TerrainOceanBlockIndex" = "18" /
       "TemperatureOffset" = "0" /
       "HumidityOffset" = "0" /
       "SeaLevelOffset" = "0" /
       "BiomeSize" = "1" /
       "BlockTextureName" Type = "PhF 2.1 plus.png.scbtex" /
       "Palette"
          "Colors" = ";;;;;;;;;;;;;;;" /
          "Names" Type = ";;;;;;;;;;;;;;;" /

       "WorldSeed" = "137277" /
       "TotalElapsedGameTime" = "6367149.0882766638" /

Many of these entries are set by the OPTIONS during normal world
generation. Some may be changed afterward, depending on the current game
mode.

#### Hacking Game Info

The following items are useful to edit:

  - Game Mode: Put the game into the specified mode. (This is the only
    way to get out of Cruel mode.) The accepted modes are: Cruel,
    Challenging, Harmless, Creative and Adventure. Only these exact
    words will be accepted.

<!-- end list -->

  - WorldSeedString: This is the string entered when the world was
    created. It will be blank if a random seed was used. You CAN use
    this string to create a new "identical" world (if it isn't blank).

<!-- end list -->

  - TerrainOceanBlockIndex: The ocean is made up of the block id
    specified here. Only works on flat worlds and the id must represent
    a valid block.

<!-- end list -->

  - TemperatureOffset and HumidityOffset: These represent the overall
    world's base settings. They reflect the values chosen when the world
    was created.

<!-- end list -->

  - SeaLevelOffset: This sets the level of water throughout the world.
    By editing this in a non-flat world, the water can be made to cover
    more of the land. In-game the ocean may be raised up to 16 blocks.
    By editing the xml, it can be raised further if you want a deeper
    ocean with much less land mass. It may even be edited to a negative
    number but this will often cause strange effects:

<div style="overflow:hidden">

![Survivalcraft_2018-07-07_11-51-44.jpg](Survivalcraft_2018-07-07_11-51-44.jpg
"Survivalcraft_2018-07-07_11-51-44.jpg")

</div>

This can be avoided by editing the world before adding a player. (See
below.)

  - BiomeSize: Controls the relative sizes of the biomes. Normally
    between 1 and 3. If it's set to smaller values than 1, very small
    and strange terrain biomes are generated. This can be set to
    "Infinity" to create a single, huge biome. It can also be set to 0
    but very strange effects will take place.

<!-- end list -->

  - BlockTextureName: Shows the name of the texture pack chosen for this
    world.

<!-- end list -->

  - Palette: Used when the palette colors are different than the default
    ones.

<!-- end list -->

  - WorldSeed: This is internal seed created by the game, to identify
    this particular terrain generation. It is NOT the same as what is
    entered when creating a new world. You can NOT use this when
    creating a new world, hoping it will make the same one.

<!-- end list -->

  - TotalElapsedGameTime: displays the total play time in the game since
    it was first created.

Also, see below for more detailed "World Modifications" which can be
made to this section.

### Player Specific Sections

There are three sections devoted to information about the player(s).
"PlayerStats" holds the details of what the player has done in the past.
"Players" holds the system-related specifications for that player (see
below). Player (entity) holds all the current data for the player, such
as current location, hunger, inventory, etc.

#### Player Stats

Since 2.0, the game keeps track of more information about the characters
(players). Most of these stats are shown on the pause screen. There is
little point in modifying them since they represent past 'achievements'.

Here is a typical entry for this section:

```
    "PlayerStats"
      "Stats"
        "1"
          "DistanceTravelled" = "153106.8052464803"
          "DistanceWalked" = "106555.81852962566"
          "DistanceFallen" = "44113.418842129344"
          "DistanceClimbed" = "0"
          "DistanceFlown" = "0"
          "DistanceSwam" = "43.043845433596289"
          "DistanceRidden" = "2394.508053181893"
          "LowestAltitude" = "3.9999997615814209"
          "HighestAltitude" = "112.225341796875"
          "DeepestDive" = "1.7996444702148438"
          "Jumps" = "14119"
          "BlocksDug" = "12762"
          "BlocksPlaced" = "3493"
          "BlocksInteracted" = "2391"
          "PlayerKills" = "0"
          "LandCreatureKills" = "282"
          "WaterCreatureKills" = "2"
          "AirCreatureKills" = "93"
          "MeleeAttacks" = "1163"
          "MeleeHits" = "1132"
          "RangedAttacks" = "177"
          "RangedHits" = "104"
          "HitsReceived" = "224"
          "StruckByLightning" = "1"
          "TotalHealthLost" = "28.515389336273074"
          "FoodItemsEaten" = "172"
          "TimesWasSick" = "0"
          "TimesHadFlu" = "0"
          "TimesPuked" = "0"
          "TimesWentToSleep" = "123"
          "TimeSlept" = "36491.68495955877"
          "ItemsCrafted" = "2765"
          "FurnitureItemsMade" = "0"
          "EasiestModeUsed" =  "Challenging"
          "HighestLevel" =  "20.736208"
          "DeathRecordsString" =  "3.4306013577994112,306.019684,64.0674744,206.587173,mauled by a brown bear;"
```

#### Players

This will show certain details for each player in the world. There will
be an entry for each player.

Here is a typical entry for one player:

```
  "Players"
    "NextPlayerIndex" Type="int" Value="2"
    "GlobalSpawnPosition" Type="Vector3" Value="-44.8986778,65.35824,18"
    "Players"
      "1"
        "SpawnPosition" = "466.25,64.1,-8.25"
        "FirstSpawnTime" = "0.016241099685430527"
        "LastSpawnTime" = "4462.9115594206378"
        "SpawnsCount" = "11"
        "Name" = "Explorer"
        "PlayerClass" = "Male"
        "Level" = "20.736208"
        "CharacterSkinName" = "Explorer.scskin"
        "InputDevice" = "None"
```

#### Player (Entity)

Here is a typical entry:

```
  <Entities>
    "1" Guid="bef1b918-6418-41c9-a598-95e8ffd39ab3" Name="MalePlayer">
      "Player">
        "ConstantSpawn" = "False"
        "PlayerIndex" = "1"
      "Locomotion"
        "IsCreativeFlyEnabled" = "False"
      "Health"
        "Health" = "1"
        "Air" = "1"
      "Intro"
        "PlayIntro" = "False"
      "Sickness"
        "SicknessDuration" = "0"
      "Body">
        "Position" = "340.25,54,236.20903"
        "Rotation" = "0,-0.342197448,0,0.939628065"
        "Velocity" = "0,0,5.20547039E-13"
      "Gui">
        "KeyboardHelpMessageShown" = "False"
        "GamepadHelpMessageShown" = "False"
      "FurnitureInventory">
        "FurnitureSet" = ""
      "Spawn">
        "SpawnTime" = "4462.9115594206378"
      "Inventory">
        "Slots">
          "Slot0">
            "Contents" = "38"
            "Count" = "1"
          "Slot1">
            "Contents" = "36"
            "Count" = "1"
          "Slot2">
            "Contents" = "3932197"
            "Count" = "1"
          "Slot3">
            "Contents" = "31"
            "Count" = "39"
          "Slot4">
            "Contents" = "67633343"
            "Count" = "1"
. . .
          "Slot21">
            "Contents" = "65709"
            "Count" = "23"
        "ActiveSlotIndex" = "5"
      "Flu">
        "FluDuration" = "0"
        "FluOnset" = "0"
      "Clothing">
        "Clothes">
          "Head" = ""
          "Torso" = ""
          "Legs" = ""
          "Feet" = ""
      "Sleep">
        "SleepStartTime" = "0"
        "AllowManualWakeUp" = "True"
      "CraftingTable">
        "Slots"
      "VitalStats">
        "Food" = "0.9906888"
        "Stamina" = "1"
        "Sleep" = "0.590762258"
        "Temperature" = "18.7428932"
        "Wetness" = "0"
        "Satiation">
          "89" = "1.66374815"
      "OnFire">
        "FireDuration" = "0"
      "CreativeInventory">
        "ActiveSlotIndex" = "0"
        "CategoryIndex" = "0"
        "PageIndex" = "0"
        "Slots"
```

#### Useful Changes

  - If you change the player's 'HEALTH' to "Infinity", you are
    essentially invincible and can fly high above the world or even
    underneath it and are not damaged. You cannot even 'suicide'. Health
    is normally from 0 (dead) to 1 (full health). This value is found in
    the Player (entity) section.

<!-- end list -->

  - You can set things like what is in the character's inventory and
    what clothing it is wearing. The section labelled "Inventory" has a
    total of 21 slots. This is because the first 6 (0-5) refer to the
    hotbar slots. There is a separate entry for the inventory seen when
    in creative mode, called "CreativeInventory". In this example it's
    empty. The personal crafting space has its own entry as well.

<!-- end list -->

  - You can enable flying even in non-creative modes by changing
    "IsCreativeFlyEnabled" to "True".

### Memory Bank

This is an example code for the MemoryBankBlockBehavior section in a
sample xml file:

    "[b]MemoryBankBlockBehavior[/b]"
       "[b]Blocks[/b]"
          "3405,66,5002" = "FEDCBA9876543210;3"
          "3403,65,5004" = "000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000F;0"
       "[b]Items[/b]"

That is the code for two banks placed and programmed with data.

What that code means:

"MemoryBankBlockBehavior" has two sub-heads - "Blocks" and "Items".

The "Blocks" heading lists every bank by a unique 'Name', which is
actually their location. Each bank in this list has two values. The
first value is the data in that bank. The second value is the data that
is currently being output by the bank.

As you can see, the programmed data assumes all trailing data are '0's.
The first bank was only programmed in the first row, so the remaining
data are all '0's. The second bank was only programmed in the last cell
so all leading data was fillled in as '0's. The first bank has a battery
connected to the AddressLow input which is supplying a steady voltage
value of 'C' to the input. This causes the bank to output a '3' as
indicated. The second bank has nothing connected to the address inputs
and accordingly is outputting a '0'.

The "Items" heading works similar to the "Blocks" heading but with one
small difference: every unique 'Name' associated with item's data.

Note that this is NOT the block data for the memory bank so does not
include the bank's orientation or connections. That information is
inside the chunks file.

This means that it is possible to program every bank in a world, and set
its current state outside of the game itself.

### Truth Table

The xml code for a truth table entry is:

    "[b]TruthTableCircuitBlockBehavior[/b]"
       "[b]Blocks[/b]"
          "3407,66,4999" = "0F0000000000000F"
       "[b]Items[/b]"

The structure is the same as for the Memory Bank. It has two
sub-headings, "Blocks" and "Items". Each table listed in the block
section is also identified by its location. There is only a single value
for each table and this tells how it is programmed. Each digit in the
string represents one checkbox in the table's interface. The left-most
digit is the top box, etc. Where the box is checked, an 'F' is present
in the file.

This shows that through the xml file, we can do something that cannot be
done 'normally', however\! Each input and the output are normally
assumed to be binary (digital). But, the above data shows that the
output may be treated as a hexadecimal (analog) value. Rather than
outputting an 'F' (digital '1') the table can actually output ANY hex
value. This feature gives us more flexibility in the Truth Table
although it can only be utilized via editing the xml file. And it has
been verified to work.

### Furniture

There are two general entries for furniture use. The first is for each
furniture design and the second is for furniture packs.

This is an example basic entry for a furniture design:

```
  Name = "4"
    Name = "Stone light"
    TerrainUseCount = "71"
    Resolution = "15"
    InteractionMode = "None"
    Values = "1582*0,1*26,14*0,1*79903,14*0,1*26,14*0,1*26,14*0,1*26,1732*0,"
```

There are 6 fields in this entry:

  - The first Name is the internal reference to this particular
    furniture design. The game assigns this unique number to each
    design.
  - The second Name is what the player named this design.
  - The third field, "TerrainUseCount" keeps track of how many times
    this design is used in the world. If it is '0' and the design is not
    included in a furniture pack, it will be deleted by the game.
  - The fourth field records the resolution, or initial size of the
    design. This can be from 2 to 16.
  - The fifth field, "InteractionMode" tells the system what 'type' of
    furniture this piece is. The valid values are: "None",
    "ElectricButton", "ElectricSwitch", "Interactive" and "Connected".
  - The last field holds the actual design parameters of this piece. It
    calls out the BlockID and the amount of those blocks, using a
    defined starting point and pattern. The first entry in the above
    example is "1582\*0" and tells there are 1582 blocks of air ('0')
    before the first non-air block is found.

If the design is a switch, interactive or connected type, there will be
an additional field:

```
  "LinkedDesign" = "56" />
```

This is how each different design for a changing piece is defined and it
creates a "linked list". The value specifies the next design in this
list and refers to the first 'Name' in the entry (the number). For a
toggle switch, there will only be two designs in the list. For others,
there may be up to 9 different designs. See below, "Infinite State
Blocks".

#### Hacking Furniture

  - **Unsuitable Blocks**

There are several blocks that are not acceptable in normal furniture
creation, such as dirt, leaves and trees (wood). By editing the
furniture in the xml, these blocks can be incorporated into a furniture
design. Many of these unsuitables will not turn out as expected. In
particular, any items with a 3-D model or ones that are 'activated'
blocks, such as grass (not dirt) or furnace may not work well.

The easiest way is to create the design you want, using a unique block
where you want the unsuitable block to be. Use a block which you know
the block ID of, and which is not used anywhere else in the design. Then
edit the xml to find that furniture design. Within the design, locate
the place(s) where the unique block is and simply replace its ID with
the ID of the unsuitable block.

  - **Infinite-State Blocks**

Interactive blocks have several states. As described above, these states
form a 'linked list'. The limit of 9 states is a block is imposed by the
crafting table, not by the furniture itself since linked lists have no
inherent limit. In a linked list, each state has a pointer to the next
state. The 'final' state simply points back to the first state, so a
circle is formed. By editing the list pointers, we can do several things
not possible in-game. These are all accomplished by simply changing the
"LinkedDesign" pointers.

1.  The list can be extended to any length desired.
2.  The piece does not have to repeat - it can be made to 'freeze' in
    one specified state, by specifying the LinkedDesign as the current
    state.
3.  The piece can go through some states only once and then repeat in a
    pattern which doesn't include those states. This includes the
    possibility of one piece 'morphing' into another. Instead of the
    last state linking to the first, it can link to any one along the
    chain.
4.  Using the above idea, two apparently different pieces can 'morph'
    into the same one.

### Furniture Packs

Here is a sample entry for a furniture pack (set):

```
  Name = "0"
    Name = "Hexkeys"
    ImportedFrom = "Hexkeys.scfpack"
    Indices = "0;1;2;3;4;5;6;7;8;9;10;11;12;13;14;15"
```

As in furniture pieces, the first "Name" is assigned by the game. The
second "Name" is the name given by the creator of the pack. This third
field, "ImportedFrom" defines the file this pack was saved as. It will
not be included if the pack was created in the current world. The last
field, "Indices" specifies which individual pieces are included in this
furniture pack.

#### Hacking Furniture Packs

There isn't much to do with the packs other than manually add or delete
pieces from them, or rearrange the order the pieces are displayed in.

To add pieces to the pack you need to know the internal number of the
item you want to add. See the section on furniture pieces. This will
show you how to find the number of the piece. Once you have those
numbers just add them in the "Indices" list like it shows above.

To delete pieces, simply delete the proper piece number from the list
(and one semicolon before or after it).

Rearranging the displayed order is probably the most useful hack. If you
have a multi-piece furniture design it can be quite helpful to have the
separate pieces displayed in a particular order to make it easier to
assemble them correctly. You first need to set the order you want them
in. Then find the internal number for each of those pieces. Finally fill
in the "Indices" list with them in the order you need them.

A particular piece can't be in several packs at the same time. If you
hack 'Indices' in such a way that the ID of some furniture appears in
two different sets of furniture, then these furniture designs will
remain only in the last set from the 'FurnitureSets' list where they are
mentioned.

One piece can't be in the same pack multiple times. All identical IDs in
'Indices', except the first, will be deleted.

### Moving Blocks

This section is meant as support for falling blocks and it keeps track
of blocks being moved by pistons. Moving blocks are defined in sets
since there is often more than a single block moving together.

This is a sample (stripped-down) entry:

```
 MovingBlocks
   MovingBlockSets
     Name="0">
       "Position" = "128,69.7492752,941" />
       "TargetPosition" = "128,-2,941" />
       "Speed" = "1.91046238" />
       "Acceleration" = "10" />
       "Drag" = "0.7" />
       "Id" = "CollapsingBlock" />
       "Blocks" = "7,0,0,0;" />
```

This is an example entry for a single falling block of sand.

  - Position is the current location of the 'reference block' for the
    group.
  - TargetPosition is the final position when motion will stop. For all
    falling blocks this is set to -2. For blocks being moved by pistons,
    this is determined by the setting and location of the piston.
  - Speed is the group's current speed of movement.
  - Acceleration is set to "10" for falling groups and "0" for piston
    groups.
  - Drag is non-zero in this example. This particular block is falling
    while up against a wall, causing the drag.
  - Smoothness is present in piston-based groups and is a 2-valued
    vector.
  - Id indicates the type of group this is. So far, the only known
    acceptable values are "CollapsingBlock" and "Piston".
  - A "Tag" entry is present in piston-based groups and defines the
    position of the piston block for this group.
  - The "Blocks" entry lists the blocks that make up this group. Each
    block has a 4-valued entry where the first value is the block ID and
    the rest are its location relative to the 'reference block'. One
    block will always have "n,0,0,0" showing it's the reference block.

In piston groups the blocks field includes the moving parts of the
piston as well. The 'face' of the piston is the reference point. Each
extended (full and partial) block of the plunger is also included. Thus
a piston's moving group may consist of up to 16 blocks.

#### Hacking 'Moving Blocks'

Thanks to @Lion, from the russian SC community, for discovering the
unique things we can do by modifying this section.

You can (theoretically) make a huge building move across the ground or
blocks that shoot up into the sky and go on forever. Or make a
'levitation' path that can hold the character above ground without any
visible indication of its presence. First it is necessary to explore and
define certain characteristics of freely moving blocks and piston-driven
groups.

Several characteristics of the piston group are crucial to these hacks.

  - While the group is "moving" (whether or not it currently is in
    motion) the blocks are NOT included in the blocks file because they
    are not stationary and are only defined in this section.
  - The TAG entry is meant to reference the location of the piston for
    the group. These hacks take advantage of the unexpected behavior of
    groups without a piston in the TAG position.
      - If a piston is not present at that location, a moving group will
        pass right through normal blocks. Another moving group in the
        way WILL however pause this movement.
      - If a piston is later placed or moved into the TAG position, the
        group will 'attach' itself to the piston and begin behaving
        normally.
  - A block ID of '0' may be used for blocks in the group. This creates
    an 'imaginary' block which will still stop movement of another group
    but has no other physical effect.
  - As is normal for piston group behavior, one moving group will stop
    another until the first one is no longer in the way. Then the second
    group will continue its motion.
  - A moving group will pull the character that is standing on top of it
    along with it even if the group is paused (by another group). This
    applies to animals as well but not to blocks or debris. In most
    'normal' cases this is so small an effect that it is not noticeable.
    However if the speed is set quite high (1000) then it will pull the
    character along its movement direction quite fast. This feature is
    used to creat the "slideway" and "levitation" hacks.

When blocking one group with another it may be helpful to place the
stationary group (or block) so that it is in the path of the reference
block of the 'moving' group.

HACK 1: Create moving constructions that don't have pistons.

Create a structure of "any" size and shape in a single group. Leave the
Tag location with NO piston. Set the TargetPosition field to its final
destination. It will immediately begin moving when the game is started
and not stop until it reaches that location, even passing through solid
blocks\!

You may wish to use HACK 3 to have it start "on command". The same hack
can be used to have it pause at specified 'stopovers'.

HACK 2: Create untouchable blocks.

Create a group of blocks not tagged to a piston. Set their speed to '0'
so they do not move. These blocks cannot be built upon or moved by the
player, even using pistons. The character cannot move through them or
affect them with any tools. "Better than bedrock\!"

  - This hack may be used to start and stop other moving groups. One of
    these untouchable blocks is put in the way of another (hacked)
    moving group. The group does not pass through this block so is
    paused. The SPEED of the paused group does not change while it is
    paused. Then a piston is put into the untouchable blocks's TAG
    location, which changes it into a 'normal' block. The hacked group
    will then pass through this normal block and begin its movement. To
    stop the moving group, just have another untouchable block in its
    way where you want it to stop.

HACK 3: Create an automated personnel "slideway".

1.  Create a moving group shaped like a long ribbon on the ground. Set
    "TargetPosition" to a location well beyond its terminal end. Set
    "Speed" to a high value such as 1000. Make sure there is no piston
    at the "Tag" location.
2.  Create another group (or just 1 block) in the way of the first group
    to make it pause. This second group has a "Speed" of '0'and could
    use ID0 'blocks'. Make sure there is no piston at the "Tag"
    location. The second group permanently prevents the first group, the
    ribbon, from actually moving.

Here's an example slideway:

```
      "0"
          "Position" = "-179,20,-109"
          "TargetPosition" = "-179,20,-1000"
          "Speed" = "100"
          "Acceleration" = "0"
          "Drag" = "0"
          "Smoothness" = "0,0.5"
          "Id" = "Piston"
          "Tag" = "-170,15,-152"
          "Blocks" = "147459,0,0,0;147459,1,0,0;147459,2,0,0;147459,0,0,1;147459,1,0,1;147459,2,0,1;147459,0,0,2;147459,1,0,2;147459,2,0,2;147459,0,0,3;147459,1,0,3;147459,2,0,3;147459,0,0,4;147459,1,0,4;147459,2,0,4;147459,0,0,5;147459,1,0,5;147459,2,0,5;147459,0,0,6;147459,1,0,6;147459,2,0,6;147459,0,0,7;147459,1,0,7;147459,2,0,7;147459,0,0,8;147459,1,0,8;147459,2,0,8;147459,0,0,9;147459,1,0,9;147459,2,0,9;147459,0,0,10;147459,1,0,10;147459,2,0,10;147459,0,0,11;147459,1,0,11;147459,2,0,11;147459,0,0,12;147459,1,0,12;147459,2,0,12;147459,0,0,13;147459,1,0,13;147459,2,0,13;147459,0,0,14;147459,1,0,14;147459,2,0,14;147459,0,0,15;147459,1,0,15;147459,2,0,15;147459,0,0,16;147459,1,0,16;147459,2,0,16;"
      "1"
          "Position" = "-178,20,-110"
          "TargetPosition" = "-179,20,-1000"
          "Speed" = "0"
          "Acceleration" = "0"
          "Drag" = "0"
          "Smoothness" = "0,0.5"
          "Id" = "Piston"
          "Tag" = "-170,15,-148"
          "Blocks" = "4,0,0,0;"
```

The first group is the 'slideway' surface. The second group (block)
pauses the motion of the first group.

HACK 4: Create a levitating or magnetic surface.

This is similar to the slideway hack but instead of a fast movement in a
horizontal direction this creates a movement upwards and uses the
'untouchable blocks'. When the character jumps into one of these blocks
the upwards movement will compensate for gravity and hold him in place.
He can still move back and forth. To leave the levitation field you just
move out from 'under' it.

1.  Create a flat surface of your deisred shape, using any block ID. Set
    the "Speed" to 4.5. (This compensates for gravity's effect. Set
    "TargetPosition" to something well above the height of this surface.
    Make sure there is no piston at the "Tag" location.
2.  Create another group (or just 1 block) in the way of the first group
    to make it pause. This second group has a "Speed" of '0'and could
    use ID0 'blocks'. The second group permanently prevents the first
    group, the ribbon, from actually moving. Make sure there is no
    piston at the "Tag" location.

Here's an example levitating strip:

    ﻿      "9"
              "Position" = "-165,10,-169"
              "TargetPosition" = "-165,100,-169"
              "Speed" = "4.5"
              "Acceleration" = "0"
              "Drag" = "0"
              "Smoothness" = "0,0.5"
              "Id" = "Piston"
              "Tag" Type= "Point3" Value= "-161,10,-164"
              "Blocks" = "23,0,0,0;23,1,0,0;23,2,0,0;23,3,0,0;23,4,0,0;23,5,0,0;23,6,0,0;23,7,0,0;23,8,0,0;23,9,0,0;23,10,0,0;23,11,0,0;23,12,0,0;23,0,0,1;23,1,0,1;23,2,0,1;23,3,0,1;23,4,0,1;23,5,0,1;23,6,0,1;23,7,0,1;23,8,0,1;23,9,0,1;23,10,0,1;23,11,0,1;23,12,0,1;"
         "11"
              "Position" = "-165,11,-169"
              "TargetPosition" = "-141,100,-153"
              "Speed" = "0"
              "Acceleration" = "0"
              "Drag" = "0"
              "Smoothness" = "0,0.5"
              "Id" = "Piston"
              "Tag" Type= "Point3" Value= "-155,10,-164"
              "Blocks" = "0,0,0,0;"

The first group is the 'levitating' surface. The second group (block)
pauses the motion of the first group.

### Weather

    <Values Name="Weather">
          <Value Name="WeatherStartTime" Type="double" Value="31195.27074897592" />
          <Value Name="WeatherEndTime" Type="double" Value="31383.926867786096" />
          <Value Name="LightningIntensity" Type="float" Value="0.9715154" />

'LightningIntensity' can be 0 to 1.

### Signs

Here's a typical sign entry:

    (    <Values Name="SignBlockBehavior">
          <Values Name="Texts">)
    --- SIGN ENTRY: ---
            <Values Name="0">
              <Value Name="Point" Type="Point3" Value="11,66,-20" />
              <Value Name="Line1" Type="string" Value="blue" />
              <Value Name="Line2" Type="string" Value="white" />
              <Value Name="Color1" Type="Color" Value="0,0,96" />
              <Value Name="Color2" Type="Color" Value="180,180,180" />
              <Value Name="Url" Type="string" Value="http:blome" />
            </Values>
          </Values>
        </Values>

The first line has the unique identified the game assigns to each sign.
The next line ("Point") is the location of the sign in the world
coordinates.

Next, each line of text is listed after "Line1", "Line2", etc. The
colors of each line are listed similarly. "Color1" is the color of the
text in Line1, etc.

The line "Url" holds the web address the sign will open if tapped in
adventure mode. (See [Sign](Sign "wikilink").)

#### Custom text colors

You can make the color of the text to be any color you choose.

The three values in the 'color' fields specify an "xna frameworks"
color. This is a standard way to define colors and is used throughout
the internet. Each number can be from 0 to 255. The first one is the
amount of red in the final color. The second is the amount of green, and
the third is blue.

You can reference a standard color chart to find the color and value you
wish.

### Entities

Here is a part of a typical entities section:

```
    <Entity Id="2" Guid="c7dfa822-ba6e-4f3f-905c-0241823edf15" Name="Ray_Brown">
      <Values Name="Locomotion">
        <Value Name="IsCreativeFlyEnabled" Type="bool" Value="False" />
      </Values>
      <Values Name="Creature">
        <Value Name="ConstantSpawn" Type="bool" Value="False" />
      </Values>
      <Values Name="Spawn">
        <Value Name="SpawnTime" Type="double" Value="362.393716359511" />
      </Values>
      <Values Name="Loot">
        <Value Name="LootDropped" Type="bool" Value="False" />
      </Values>
      <Values Name="Body">
        <Value Name="Position" Type="Vector3" Value="406.512665,62.4463348,56.9966545" />
        <Value Name="Rotation" Type="Quaternion" Value="0,0.436656624,0,0.8996283" />
        <Value Name="Velocity" Type="Vector3" Value="-0.639416754,-0.09736531,-0.496444345" />
      </Values>
      <Values Name="Health">
        <Value Name="Health" Type="float" Value="1" />
        <Value Name="Air" Type="float" Value="1" />
      </Values>
      <Values Name="OnFire">
        <Value Name="FireDuration" Type="float" Value="0" />
      </Values>
    </Entity>
    <Entity Id="3" Guid="f00144f5-ede0-461c-96f9-2206babbbf06" Name="Bison">
      <Values Name="Creature">
        <Value Name="ConstantSpawn" Type="bool" Value="False" />
      </Values>
      <Values Name="Locomotion">
        <Value Name="IsCreativeFlyEnabled" Type="bool" Value="False" />
      </Values>
      <Values Name="Loot">
        <Value Name="LootDropped" Type="bool" Value="False" />
      </Values>
      <Values Name="Body">
        <Value Name="Position" Type="Vector3" Value="403.7786,63.76605,85.55463" />
        <Value Name="Rotation" Type="Quaternion" Value="0.000128486674,0.9976713,-0.0018801156,0.0681806356" />
        <Value Name="Velocity" Type="Vector3" Value="-0.0159330163,0.0493074059,0.188022658" />
      </Values>
      <Values Name="OnFire">
        <Value Name="FireDuration" Type="float" Value="0" />
      </Values>
      <Values Name="Health">
        <Value Name="Health" Type="float" Value="1" />
        <Value Name="Air" Type="float" Value="1" />
      </Values>
      <Values Name="Spawn">
        <Value Name="SpawnTime" Type="double" Value="358.38871435076" />
      </Values>
    </Entity>
    <Entity Id="4" Guid="60dc514b-2b8e-40a7-9bc3-09bb1efe0732" Name="Raven">
      <Values Name="Locomotion">
        <Value Name="IsCreativeFlyEnabled" Type="bool" Value="False" />
      </Values>
      <Values Name="Creature">
        <Value Name="ConstantSpawn" Type="bool" Value="False" />
      </Values>
      <Values Name="OnFire">
        <Value Name="FireDuration" Type="float" Value="0" />
      </Values>
      <Values Name="Body">
        <Value Name="Position" Type="Vector3" Value="439.135132,73.6557846,101.548668" />
        <Value Name="Rotation" Type="Quaternion" Value="0,0.667251945,0,0.7448321" />
        <Value Name="Velocity" Type="Vector3" Value="-3.11229944,0.991040468,-0.7202861" />
      </Values>
      <Values Name="Loot">
        <Value Name="LootDropped" Type="bool" Value="False" />
      </Values>
      <Values Name="Health">
        <Value Name="Health" Type="float" Value="1" />
        <Value Name="Air" Type="float" Value="1" />
      </Values>
      <Values Name="Spawn">
        <Value Name="SpawnTime" Type="double" Value="354.37284226063639" />
      </Values>
    </Entity>
    <Entity Id="5" Guid="abf17893-e4d4-4638-943d-50a545761ecc" Name="Piranha">
      <Values Name="Creature">
        <Value Name="ConstantSpawn" Type="bool" Value="False" />
      </Values>
      <Values Name="Locomotion">
        <Value Name="IsCreativeFlyEnabled" Type="bool" Value="False" />
      </Values>
      <Values Name="Spawn">
        <Value Name="SpawnTime" Type="double" Value="362.393716359511" />
      </Values>
      <Values Name="Loot">
        <Value Name="LootDropped" Type="bool" Value="False" />
      </Values>
      <Values Name="Health">
        <Value Name="Health" Type="float" Value="1" />
        <Value Name="Air" Type="float" Value="1" />
      </Values>
      <Values Name="Body">
        <Value Name="Position" Type="Vector3" Value="366.109283,62.91997,73.52771" />
        <Value Name="Rotation" Type="Quaternion" Value="0,0.8390603,0,0.5440384" />
        <Value Name="Velocity" Type="Vector3" Value="-0.9491566,0.08113135,0.3140725" />
      </Values>
      <Values Name="OnFire">
        <Value Name="FireDuration" Type="float" Value="0" />
      </Values>
    </Entity>
```

This particular section has entries for 4 entities - a Brown Ray, a
Bison, a Raven and a Piranha.

#### Entities mods

This is a list of things that can be done by editing entity section;

\-teleport player/animals (by editing position) including in the Far
Lands.![Uyrjhfdjh.jpg](Uyrjhfdjh.jpg "Uyrjhfdjh.jpg")

\-make player/animals immortal (by editing health in vital stats)

\-make animals fly in creative (by enabling creative flying mode)
![Survivalcraft_2019-11-16_17-50-50_(3).jpg](Survivalcraft_2019-11-16_17-50-50_\(3\).jpg
"Survivalcraft_2019-11-16_17-50-50_(3).jpg")

\-spawn rare animals by putting in their data:

White Tiger:

`"6effc493-b96a-4168-8855-9f3dd2f1af85" Name="Tiger_White">`

White Bull:

`"eaef1318-a143-4013-9354-bbe37a611285" Name="Bull_White">`

Orca:

`"78605a8d-e335-49b4-867d-5b4555e02fd4" Name="Orca">`

Beluga:

`"2260c463-4dfd-4395-aa25-28ba876ed391" Name="Beluga">`

\-despawn animals. They just disappear, like dead animals do. (by adding
DespawnTime value)![Despawningblackhorse.jpg](Despawningblackhorse.jpg
"Despawningblackhorse.jpg")

\-bring animals from the dead. Only works when the body still exists.
(by modifying health and removing deathtime, despawntime and deathcause)

\-make indestructable boat (by editing hitpoint of the boat) - With
this, you can travel in magma\! Sadly the heat will kill you.

\-riding any animal (while riding any rideable animal, save the game and
replace the rideable animal to any of you want or add ParentBody
value)![Survivalcraft_2019-11-16_18-00-44_(2).jpg](Survivalcraft_2019-11-16_18-00-44_\(2\).jpg
"Survivalcraft_2019-11-16_18-00-44_(2).jpg")![Osouuuuuuuuuuuurrrrrrrrrrrrrrrrr.jpg](Osouuuuuuuuuuuurrrrrrrrrrrrrrrrr.jpg
"Osouuuuuuuuuuuurrrrrrrrrrrrrrrrr.jpg")

\-If you type in coordinates in the magnet behavior, you can get an
invisible magnet at that location.

## World modification

Most of the entries in the project file are related to things inside the
world but some entries are about the world itself.

### Flatten portions of the world

You can have a world with only certain areas modified to “Flat”. These
areas could be at any level you wish, except 255 and more. The rest of
the world may be generated normally with common terrain features.

How it works:

The game has a terrain generator that creates the untouched world
without saving any parts of it. But once any block is added, broken or
changed by the player, it no longer can use the generator and the chunk
that the block was in must be saved as it is. The saved chunks are in
the chunks32.dat file. (We will not modify that file, here.)

The terrain generator *can* be affected by some settings in the project
file. These changes do not affect the chunks already stored in the
chunks file, only ones that were never modified.

This procedure will "lock in" only certain chunks (by modifying them)
but let other chunks change according to the new settings. Then those
chunks may be "locked in" at the new settings.

#### The Process

1.  create a random or seeded world
2.  mark any chunks you wish to keep as normal terrain (place or remove
    any block in that chunk)
3.  exit the world and save it to SD
4.  open that world’s xml file
5.  change terrain type to "Flat"
6.  set new terrain level
7.  set terrain block type as wanted
8.  save the xml file
9.  load the world into SC and open it
10. mark all chunks to keep at that new level
11. exit the world and save it to SD
12. open that world’s xml file
13. change back to Normal terrain and level 64
14. save the xml file
15. load the world into SC and open it

You now have a ‘normal’ world with deep pits or high towers of flat
terrain. You can repeat this process for any other levels you wish,
higher or lower than normal. These will be flat with the terrain block
specified.

### Worlds without people

Some changes are affected by whether a chunk has been 'spawned' already
or not. You can avoid this in new worlds by creating a world without a
player character in it. Such a world cannot be opened normally but it
can be saved and edited. There will be no sections for player info so
you can't hack anything in there. But there is also no "Spawn" /
"Chunks" section and so is an untouched, pristine world.

Doing so is simple. Create your new world as you want it set up and
enter the "SETUP PLAYER" screen but tap the BACK arrow instead of OK.
The world may be saved and edited as any other.

### Other World mods

If you start with a “Flat” world, you could change it to Normal to
generate terrain but it always generates infinite ocean with islands,
even if you don’t modify it before making it “Normal”. As long as
terrain generation is “Normal”, the terrain level doesn’t seem to
matter.

## Obtaining items and blocks that are missing in the creative inventory

[The developer
wrote](https://kaalus.wordpress.com/chunks-dat-file-format/) that blocks
in chunks are written as follows:

  - Bits 0 to 9 (10 bits): [Block ID](Block_ID "wikilink")
  - Bits 10 to 13 (4 bits): Block light value (0 – complete darkness, 15
    – full sunlight)
  - Bits 14 to 31 (18 bits): Block-specific data determining state of
    the block, such as door state, water level, torch location etc.

You've probably noticed that wherever there is an item, there is a long
integer. If you open the Windows calculator, click View, Programmer,
paste in such a value and convert it to binary, you will notice that
**items are encoded exactly like blocks in chunks, but their light value
= 0**. This allows us to get any item in the game. The source code of
the game (examine the source code of Survivalcraft.exe with the dnSpy
program) contains all the possible block data.

I propose to supplement this list as follows: ID, subroutines to set
data, interesting values.

  - 77 - [Raw Bird](Raw_Bird "wikilink"), stale - 262221
  - 78 - [Cooked Bird](Cooked_Bird "wikilink"), stale - 262222
  - 88 - [Raw Meat](Raw_Meat "wikilink"), stale - 262232
  - 89 - [Cooked Meat](Cooked_Meat "wikilink"), stale - 262233
  - 110 - [Milk](Milk "wikilink"), stale - 262254
  - 118 - [Eggs](Eggs "wikilink")

| Value      | Description                |
| ---------- | -------------------------- |
| 12058742   | Orca Spawner               |
| 12320886   | Beluga Spawner             |
| 1572982    | White Bull Spawner         |
| 6291574    | White Tiger Spawner        |
| 32886      | Laid Seagull Egg           |
| 295030     | Laid Duck Egg              |
| 557174     | Laid Raven Egg             |
| 8421494    | Laid Cassowary Egg         |
| 8683638    | Laid Ostrich Egg           |
| 1073774710 | Stale Laid Seagull Egg     |
| 1073741942 | Stale Seagull Egg          |
| 1073758326 | Stale Cooked Seagull Egg   |
| 1074036854 | Stale Laid Duck Egg        |
| 1074004086 | Stale Duck Egg             |
| 1074020470 | Stale Cooked Duck Egg      |
| 1074298998 | Stale Laid Raven Egg       |
| 1074266230 | Stale Raven Egg            |
| 1074282614 | Stale Cooked Raven Egg     |
| 1082163318 | Stale Laid Cassowary Egg   |
| 1082130550 | Stale Cassowary Egg        |
| 1082146934 | Stale Cooked Cassowary Egg |
| 1082425462 | Stale Laid Ostrich Egg     |
| 1082392694 | Stale Ostrich Egg          |
| 1082409078 | Stale Cooked Ostrich Egg   |

  - 131 - [Pumpkin](Recipaedia/Plants/Pumpkin.md "wikilink")

| Value  | Description                       |
| ------ | --------------------------------- |
| 114819 | Size: 0 Unripe Pumpkin            |
| 376963 | Stale Size: 0 Unripe Pumpkin      |
| 245891 | Dead Size: 0 Unripe Pumpkin       |
| 508035 | Dead Stale Size: 0 Unripe Pumpkin |
| 98435  | Size: 1 Unripe Pumpkin            |
| 360579 | Stale Size: 1 Unripe Pumpkin      |
| 229507 | Dead Size: 1 Unripe Pumpkin       |
| 491651 | Dead Stale Size: 1 Unripe Pumpkin |
| 82051  | Size: 2 Unripe Pumpkin            |
| 344195 | Stale Size: 2 Unripe Pumpkin      |
| 213123 | Dead Size: 2 Unripe Pumpkin       |
| 475267 | Dead Stale Size: 2 Unripe Pumpkin |
| 65667  | Size: 3 Unripe Pumpkin            |
| 327811 | Stale Size: 3 Unripe Pumpkin      |
| 196739 | Dead Size: 3 Unripe Pumpkin       |
| 458883 | Dead Stale Size: 3 Unripe Pumpkin |
| 49283  | Size: 4 Unripe Pumpkin            |
| 311427 | Stale Size: 4 Unripe Pumpkin      |
| 180355 | Dead Size: 4 Unripe Pumpkin       |
| 442499 | Dead Stale Size: 4 Unripe Pumpkin |
| 32899  | Size: 5 Unripe Pumpkin            |
| 295043 | Stale Size: 5 Unripe Pumpkin      |
| 163971 | Dead Size: 5 Unripe Pumpkin       |
| 426115 | Dead Stale Size: 5 Unripe Pumpkin |
| 16515  | Size: 6 Unripe Pumpkin            |
| 278659 | Stale Size: 6 Unripe Pumpkin      |
| 147587 | Dead Size: 6 Unripe Pumpkin       |
| 409731 | Dead Stale Size: 6 Unripe Pumpkin |
| 131    | Size: 7 Pumpkin                   |
| 262275 | Stale Size: 7 Pumpkin             |
| 131203 | Dead Size: 7 Pumpkin              |
| 393347 | Dead Stale Size: 7 Pumpkin        |

  - 161 - [Raw Fish](Raw_Fish "wikilink"), stale - 262305
  - 162 - [Cooked Fish](Cooked_Fish "wikilink"), stale - 262306
  - 168 - [Soil](Recipaedia/Terrain/Soil.md "wikilink")

| Value  | Description               |
| ------ | ------------------------- |
| 168    | Nitrogen: 0 Soil          |
| 16552  | Nitrogen: 0 Moist Soil    |
| 32936  | Nitrogen: 1 Compost       |
| 49320  | Nitrogen: 1 Moist Compost |
| 65704  | Nitrogen: 2 Compost       |
| 82088  | Nitrogen: 2 Moist Compost |
| 98472  | Nitrogen: 3 Compost       |
| 114856 | Nitrogen: 3 Moist Compost |

  - 174 - [Rye](Recipaedia/Plants/Rye.md "wikilink")

| Value  | Description      |
| ------ | ---------------- |
| 174    | Size: 0 Rye      |
| 131246 | Size: 0 Wild Rye |
| 16558  | Size: 1 Rye      |
| 147630 | Size: 1 Wild Rye |
| 32942  | Size: 2 Rye      |
| 164014 | Size: 2 Wild Rye |
| 49326  | Size: 3 Rye      |
| 180398 | Size: 3 Wild Rye |
| 65710  | Size: 4 Rye      |
| 196782 | Size: 4 Wild Rye |
| 82094  | Size: 5 Rye      |
| 213166 | Size: 5 Wild Rye |
| 98478  | Size: 6 Rye      |
| 229550 | Size: 6 Wild Rye |
| 114862 | Size: 7 Rye      |
| 245934 | Size: 7 Wild Rye |

  - 177 - [Bread](Bread "wikilink"), stale - 262321
  - 204 - [Cotton](Recipaedia/Plants/Cotton.md "wikilink")

| Value  | Description         |
| ------ | ------------------- |
| 204    | Size: 0 Cotton      |
| 131276 | Size: 0 Wild Cotton |
| 16588  | Size: 1 Cotton      |
| 147660 | Size: 1 Wild Cotton |
| 32972  | Size: 2 Cotton      |
| 164044 | Size: 2 Wild Cotton |

  - 239 - [Rotten Bird](Rotten_Bird "wikilink"), stale - 262383
  - 240 - [Rotten Meat](Rotten_Meat "wikilink"), stale - 262384
  - 241 - [Rotten Fish](Rotten_Fish "wikilink"), stale - 262385
  - 242 - [Moldy Bread](Moldy_Bread "wikilink"), stale - 262386
  - 244 - [Rotten Pumpkin](Recipaedia/Plants/Rotten_Pumpkin.md "wikilink")

| Value  | Description                        |
| ------ | ---------------------------------- |
| 114932 | Size: 0 Rotten Unripe Pumpkin      |
| 246004 | Dead Size: 0 Rotten Unripe Pumpkin |
| 98548  | Size: 1 Rotten Unripe Pumpkin      |
| 229620 | Dead Size: 1 Rotten Unripe Pumpkin |
| 82164  | Size: 2 Rotten Unripe Pumpkin      |
| 213236 | Dead Size: 2 Rotten Unripe Pumpkin |
| 65780  | Size: 3 Rotten Unripe Pumpkin      |
| 196852 | Dead Size: 3 Rotten Unripe Pumpkin |
| 49396  | Size: 4 Rotten Unripe Pumpkin      |
| 180468 | Dead Size: 4 Rotten Unripe Pumpkin |
| 33012  | Size: 5 Rotten Unripe Pumpkin      |
| 164084 | Dead Size: 5 Rotten Unripe Pumpkin |
| 16628  | Size: 6 Rotten Unripe Pumpkin      |
| 147700 | Dead Size: 6 Rotten Unripe Pumpkin |
| 244    | Size: 7 Rotten Pumpkin             |
| 131316 | Dead Size: 7 Rotten Pumpkin        |

  - 251 - [Pumpkin Soup](Recipaedia/Plants/Pumpkin_Soup.md "wikilink"), stale - 262395

[Category:Tips and Guides](Category:Tips_and_Guides "wikilink")
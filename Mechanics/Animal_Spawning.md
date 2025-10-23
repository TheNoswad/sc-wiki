---
title: Animal_Spawning
description: 
published: true
date: 2025-10-12T23:30:47.675Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:30:42.774Z
---

This page details the automatic and forced spawning of animals.

## Natural Spawning 

All animals have a natural habitat that they will spawn in. This does
NOT mean they won't be present in other habitats, since they will
certainly search for and follow the character. The spawning habitats for
each creature are listed below.

### Reduce Spawn Rate

  - Creatures will not spawn in bright light levels and will only spawn
    on blocks in the "TERRAIN" category. To prevent random spawning, you
    just need to either keep the area well lit OR replace all the
    'floor' with non-terrain blocks.
  - Most creatures will NOT spawn under a roof. Only ones that can spawn
    inside caves can.
  - There is a limit on how many creatures can be spawned in an area but
    this seems dependant on several conditions. But in any case if there
    are sufficient creatures with constant spawn = true (see the list
    below) already spawned in an area (18 or ??), no more are going to
    spawn. This means you can trap a bunch and this will stop more from
    spawning. Also, how wide the affected area is, is uncertain but it
    seems at least about 35 blocks from the 'stored' creatures. If you
    have supernatural creatures enabled, be aware that gray wolves lose
    Constant Spawn after shapeshifting back into a wolf so may not be
    suitable for this 'trick'.

### Spawning Procedure

Firstly, all creatures that can spawn are selected. Secondly, the
weights are summed up. Thirdly, a random number from 0 to sum is
selected. It defines the type.

| Name    | Blocks underneath   | Middle block              | Top block                 | Top block + 1  | Lighting                                  |
| ------- | ------------------- | ------------------------- | ------------------------- | -------------- | ----------------------------------------- |
| Surface | Collidable or water | Not (collidable or water) | Not (collidable or water) | Any            | SkyLightValue \>= x \>= SkyLightValue - 3 |
| Cave    | Collidable or water | Not (collidable or water) | Not (collidable or water) | Any            | 0 \<= x \<= SkyLightValue - 5             |
| Water   | Any                 | Water                     | Not collidable            | Not collidable | Any                                       |

Spawn location types used in the following lists

| Type               | Spawn location | Random | Constant | Ocean shore distance | Humidity    | Temperature                             | Altitude            | Blocks underneath                                                                                  | Weight                          | Spawn Function                                                                                                                               |
| ------------------ | -------------- | ------ | -------- | -------------------- | ----------- | --------------------------------------- | ------------------- | -------------------------------------------------------------------------------------------------- | ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| Duck               | Surface        | true   | false    | \> 30                | \> 8        | \> 4                                    | Above the top block | Oak Leaves, Birch Leaves, Spruce Leaves, Tall Spruce Leaves, Mimosa Leaves, Dirt, Grass, Water     | 2.5                             | 1 Duck                                                                                                                                       |
| Raven              | Surface        | true   | false    | \> 30                | \<= 8 or    | \<= 4                                   | Above the top block | Oak Leaves, Birch Leaves, Spruce Leaves, Tall Spruce Leaves, Mimosa Leaves, Dirt, Sand, Grass, Ice | 2.5                             | 1 Raven                                                                                                                                      |
| Seagull            | Surface        | true   | false    | \> -100; \< 40       | Any         | Any                                     | Above the top block | Gravel, Sand, Water, Ice                                                                           | 2.5                             | 1 Seagull                                                                                                                                    |
| Wildboar           | Surface        | false  | false    | \> 20                | \> 8        | Any                                     | \< 80               | Dirt, Grass                                                                                        | 0.25                            | 1 Wildboar                                                                                                                                   |
| Brown Cattle       | Surface        | false  | false    | \> 20                | \> 4        | \>= 8                                   | \< 70               | Dirt, Grass                                                                                        | 0.05                            | 3 to 5 creatures of which 1 to 3 are Bulls                                                                                                   |
| Black Cattle       | Surface        | false  | false    | \> 20                | \> 4        | \< 8                                    | \< 70               | Dirt, Grass                                                                                        | 0.05                            | 3 to 5 creatures of which 1 to 3 are Bulls                                                                                                   |
| White Bull         | Surface        | false  | false    | \> 20                | \> 8        | \< 4                                    | \< 70               | Dirt, Grass                                                                                        | 0.01                            | 1 White Bull                                                                                                                                 |
| Gray Wolves        | Surface        | false  | false    | \> 40                | \>= 8       | Any                                     | \< 100              | Dirt, Grass                                                                                        | 0.075                           | 1 to 3 Gray Wolves                                                                                                                           |
| Coyotes            | Surface        | false  | false    | \> 40                | \>= 2; \< 8 | \> 8                                    | \< 100              | Sand                                                                                               | 0.075                           | 1 to 3 Coyotes                                                                                                                               |
| Brown Bears        | Surface        | false  | false    | \> 40                | \>= 4       | \>= 8                                   | \< 110              | Dirt, Granite, Grass                                                                               | 0.1                             | 1 Brown Bear                                                                                                                                 |
| Black Bears        | Surface        | false  | false    | \> 40                | \>= 4       | \< 8                                    | \< 120              | Dirt, Granite, Grass                                                                               | 0.1                             | 1 Black Bear                                                                                                                                 |
| Polar Bears        | Surface        | false  | false    | \> -40               | Any         | \< 8                                    | \< 80               | Ice                                                                                                | 0.1                             | 1 Polar Bear                                                                                                                                 |
| Horses             | Surface        | false  | false    | \> 20                | \> 6        | \> 3; \> 8 for Palomino; \< 8 for White | \< 80               | Dirt, Granite, Grass                                                                               | 0.05                            | The following horses, one at a time, with the following probabilities: Black — 0.35, Bay — 0.5, Chestnut — 0.5, Palomino — 0.3, White — 0.3. |
| Camels             | Surface        | false  | false    | \> 20                | \< 8        | \> 8                                    | \< 80               | Sand                                                                                               | 0.05                            | 1 to 2 Camels                                                                                                                                |
| Donkeys            | Surface        | false  | false    | \> 20                | Any         | \> 6                                    | \< 120              | Dirt, Granite, Sand, Grass                                                                         | 0.05                            | 1 Donkey                                                                                                                                     |
| Giraffes           | Surface        | false  | false    | \> 20                | \> 7        | \> 8                                    | \< 75               | Dirt, Granite, Grass                                                                               | 0.03                            | 1 to 2 Giraffes                                                                                                                              |
| Rhinos             | Surface        | false  | false    | \> 40                | \> 7        | \> 8                                    | \< 75               | Dirt, Granite, Grass                                                                               | 0.04                            | 1 Rhino                                                                                                                                      |
| Tigers             | Surface        | false  | false    | \> 40                | \> 8        | Any                                     | \< 80               | Dirt, Granite, Sand, Grass                                                                         | 0.025                           | 1 Tiger                                                                                                                                      |
| White Tigers       | Surface        | false  | false    | \> 40                | Any         | \< 2                                    | \< 90               | Dirt, Granite, Sand, Grass, Ice                                                                    | 0.025                           | 1 White Tiger                                                                                                                                |
| Lions              | Surface        | false  | false    | \> 40                | Any         | \> 8                                    | \< 80               | Dirt, Granite, Sand, Grass                                                                         | 0.05                            | 1 Lion                                                                                                                                       |
| Jaguars            | Surface        | false  | false    | \> 40                | \> 8        | \> 8                                    | \< 100              | Dirt, Granite, Sand, Grass, Oak Leaves                                                             | 0.04                            | 1 Jaguar                                                                                                                                     |
| Leopards           | Surface        | false  | false    | \> 40                | Any         | \> 8                                    | \< 120              | Dirt, Granite, Sand, Grass, Oak Leaves                                                             | 0.04                            | 1 Leopard                                                                                                                                    |
| Zebras             | Surface        | false  | false    | \> 20                | \> 7        | \> 8                                    | \< 80               | Dirt, Granite, Grass                                                                               | 0.05                            | 1 to 2 Zebras                                                                                                                                |
| Gnus               | Surface        | false  | false    | \> 20                | Any         | \> 8                                    | \< 80               | Dirt, Granite, Grass                                                                               | 0.05                            | 1 to 2 Gnus                                                                                                                                  |
| Reindeers          | Surface        | false  | false    | Any                  | Any         | \< 3                                    | \< 90               | Dirt, Granite, Grass, Ice                                                                          | 0.05                            | 1 to 3 Reindeers                                                                                                                             |
| Mooses             | Surface        | false  | false    | Any                  | Any         | \< 7                                    | \< 90               | Dirt, Granite, Grass, Ice                                                                          | 0.1                             | 1 Moose                                                                                                                                      |
| Bisons             | Surface        | false  | false    | Any                  | \< 12       | \< 10                                   | \< 80               | Dirt, Granite, Grass, Ice                                                                          | 0.1                             | 1 to 4 Bisons                                                                                                                                |
| Ostriches          | Surface        | false  | false    | \> 20                | \< 8        | \> 8                                    | \< 75               | Dirt, Sand, Grass                                                                                  | 0.05                            | 1 to 2 Ostriches                                                                                                                             |
| Cassowaries        | Surface        | false  | false    | \> 20                | \< 12       | \> 8                                    | \< 75               | Dirt, Sand, Grass                                                                                  | 0.05                            | 1 Cassowary                                                                                                                                  |
| Hyenas             | Surface        | false  | false    | \> 40                | Any         | \> 8                                    | \< 80               | Dirt, Sand, Grass                                                                                  | 0.05                            | 1 to 2 Hyenas                                                                                                                                |
| Cave Bears         | Cave           | false  | false    | Any                  | Any         | Any                                     | Any                 | Dirt, Granite, Sandstone, Sand, Limestone, Basalt                                                  | 1                               | 1 Bear: Black or Brown                                                                                                                       |
| Cave Tigers        | Cave           | false  | false    | Any                  | Any         | Any                                     | Any                 | Dirt, Granite, Sandstone, Sand, Limestone, Basalt                                                  | 0.25                            | 1 Tiger                                                                                                                                      |
| Cave Lions         | Cave           | false  | false    | Any                  | \< 8        | \> 8                                    | Any                 | Dirt, Granite, Sandstone, Sand, Limestone, Basalt                                                  | 0.25                            | 1 Lion                                                                                                                                       |
| Cave Jaguars       | Cave           | false  | false    | Any                  | Any         | Any                                     | Any                 | Dirt, Granite, Sandstone, Sand, Limestone, Basalt                                                  | 0.5                             | 1 Jaguar                                                                                                                                     |
| Cave Leopards      | Cave           | false  | false    | Any                  | Any         | Any                                     | Any                 | Dirt, Granite, Sandstone, Sand, Limestone, Basalt                                                  | 0.25                            | 1 Leopard                                                                                                                                    |
| Cave Hyenas        | Cave           | false  | false    | Any                  | Any         | \> 8                                    | Any                 | Dirt, Granite, Sandstone, Sand, Limestone, Basalt                                                  | 1                               | 1 Hyena                                                                                                                                      |
| Bull Sharks        | Water          | false  | false    | \< -2                | Any         | Any                                     | Any                 | Any                                                                                                | 0.4                             | 1 Bull Shark                                                                                                                                 |
| Tiger Sharks       | Water          | false  | false    | \< -5                | Any         | Any                                     | Any                 | Any                                                                                                | 0.3                             | 1 Tiger Shark                                                                                                                                |
| Great White Sharks | Water          | false  | false    | \< -20               | Any         | Any                                     | Any                 | Any                                                                                                | 0.2                             | 1 Great White Shark                                                                                                                          |
| Barracudas         | Water          | false  | false    | \< -2                | Any         | Any                                     | Any                 | Any                                                                                                | 0.5                             | 1 Barracuda                                                                                                                                  |
| Sea Bass           | Water          | false  | false    | \< -2                | Any         | Any                                     | Any                 | Any                                                                                                | 1                               | 1 Sea Bass                                                                                                                                   |
| Freshwater Bass    | Water          | false  | false    | \> 10                | Any         | \>= 4                                   | Any                 | Any                                                                                                | 1                               | 1 to 2 Freshwater Bass                                                                                                                       |
| Rays               | Water          | false  | false    | Any                  | Any         | Any                                     | Any                 | Any                                                                                                | 0.5 if OSD \< 10, else 1        | 1 Ray: Brown if Dirt count \>= Sand count, else Yellow                                                                                       |
| Piranhas           | Water          | false  | false    | \> 10                | \>= 4       | \>= 7                                   | Any                 | Any                                                                                                | 1                               | 2 to 4 Piranhas                                                                                                                              |
| Orcas              | Water          | false  | false    | \< -20               | Any         | Any                                     | Any                 | Any                                                                                                | 0.01 if OSD \>= -100, else 0.05 | 1 Orca                                                                                                                                       |
| Belugas            | Water          | false  | false    | \< -20               | Any         | Any                                     | Any                 | Any                                                                                                | 0.01 if OSD \>= -100, else 0.05 | 1 Beluga                                                                                                                                     |

Creatures with "Constant Spawn" = false

| Type                 | Spawn location | Random | Constant | Ocean shore distance                                                                   | Humidity    | Temperature | Altitude           | Top block's lighting | Blocks underneath                | Weight | Spawn Function   |
| -------------------- | -------------- | ------ | -------- | -------------------------------------------------------------------------------------- | ----------- | ----------- | ------------------ | -------------------- | -------------------------------- | ------ | ---------------- |
| Constant Gray Wolves | Surface        | false  | true     | (OSD \> 20 and humidity \>= 8) or (temperature \<= 8 and altitude \< 90 and TBL \<= 7) | Dirt, Grass | 2           | 1 to 3 Gray Wolves |                      |                                  |        |                  |
| Constant Coyotes     | Surface        | false  | true     | \> 20                                                                                  | \< 8        | \> 8        | \< 90              | \<= 7                | Sand                             | 2      | 1 to 3 Coyotes   |
| Constant Brown Bears | Surface        | false  | true     | \> 20                                                                                  | \>= 4       | \>= 8       | \< 100             | \<= 7                | Dirt, Granite, Grass             | 0.5    | 1 Brown Bear     |
| Constant Black Bears | Surface        | false  | true     | \> 20                                                                                  | **Any**     | \< 8        | \< 110             | \<= 7                | Dirt, Granite, Grass             | 0.5    | 1 Black Bear     |
| Constant Polar Bears | Surface        | false  | true     | \> -40                                                                                 | Any         | \< 8        | \< 90              | \<= 7                | Ice                              | 0.25   | **1 Black Bear** |
| Constant Tigers      | Surface        | false  | true     | \> 20                                                                                  | \> 8        | Any         | \< 90              | \<= 7                | Dirt, Granite, Grass             | 0.05   | 1 Tiger          |
| Constant Lions       | Surface        | false  | true     | \> 20                                                                                  | Any         | \> 8        | \< 90              | \<= 7                | Dirt, Granite, Sand, Grass       | 0.25   | 1 to 2 Lions     |
| Constant Jaguars     | Surface        | false  | true     | \> 20                                                                                  | \> 8        | \> 8        | \< 100             | \<= 7                | Dirt, Granite, Grass, Oak Leaves | 0.25   | 1 Jaguar         |
| Constant Leopards    | Surface        | false  | true     | \> 20                                                                                  | Any         | \> 8        | \< 110             | \<= 7                | Dirt, Granite, Grass, Oak Leaves | 0.25   | 1 Leopard        |
| Constant Hyenas      | Surface        | false  | true     | \> 20                                                                                  | Any         | \> 8        | \< 100             | \<= 7                | Dirt, Granite, Sand, Grass       | 1      | 1 to 2 Hyenas    |

Creatures with "Constant Spawn" = true

Werewolves always have Constant Spawn = true.

Natural spawning uses 3 algorithms:

| Trigger                                                                                                           | Max executions of Spawn Function | Creatures' trait                                                | Where conditions (work at the same time)                                                                                                                                                            | Spawn conditions (work at the same time)                                                                                                                                                                                                                                          |
| ----------------------------------------------------------------------------------------------------------------- | -------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Camera within 40 blocks to a middle of a chunk; only if not visited in the last 64 in-game days (including never) | 10                               | Constant spawn = false (includes useful non-aggressive animals) | Usually 10 to 246 altitude, but can be (\> 3 and \< 253) altitude if the specified does not fit                                                                                                     | Creatures with (constant spawn = false) \< 24; creatures in 24 blocks horizontal square around the center of loading chunk with (constant spawn = false) \< 3                                                                                                                     |
| Camera within 40 blocks to a middle of a chunk                                                                    | 2                                | Constant spawn = true (only predators)                          | Usually 10 to 246 altitude, but can be (\> 3 and \< 253) altitude if the specified does not fit                                                                                                     | Creatures with (constant spawn = true) \< 18; creatures in 50 blocks horizontal square around the center of loading chunk with (constant spawn = true) \< 4                                                                                                                       |
| Every minute                                                                                                      | 1                                | Random spawn = true (only flying birds)                         | 20 to 40 blocks horizontal square around camera; usually -30 to 30 blocks around camera vertically, but can be -60 to 60 blocks around camera vertically if the previous does not fit; \> 3; \< 253 | Creatures with (constant spawn = false) \< 24; creatures in 60 blocks horizontal square around the center of camera with (constant spawn = false) \< 48; creatures in 16 blocks horizontal square around the calculated creature's spawn point with (constant spawn = false) \< 3 |

### Prevent Spawns

'Surface' means well lit, so lighting will only save from constant and
cave creatures. Against the rest, floors from the following blocks
(including painted ones) should be avoided:

| Avoid these blocks to                       | disable spawn of these types | enable spawn of these types |
| ------------------------------------------- | ---------------------------- | --------------------------- |
| Dirt, Granite, Sand, Grass, Oak Leaves, Ice | Constant                     | Not constant                |

This does NOT mean that there will not be any animals in a well-lit pen
unless the pen is also guarded by a tall fence. The fence (or wall) must
be at least 3.5 blocks tall to prevent cats from jumping into it.
Remember they often will jump and land on top of another animal — this
gives them an additional block height to jump from. If you allow
supernatural creatures (werewolves) then the fence should be even taller
— at least 4.5 blocks, if there are no blocks near the wall, or at least
5.5 blocks, if there are spikes under the wall.

### Make non-renewable animals spawn on visited chunks

Theoretically, you can replace in
[Project.xml](Hacking_The_Project_File "wikilink")
"<Value Name="IsSpawned" Type="bool" Value="True" />" to
"<Value Name="IsSpawned" Type="bool" Value="False" />". After visiting
the chunks, repeat if necessary.

## Forced Spawning Limits

![Survivalcraft_2014-12-27_08-00-05-.jpg](Survivalcraft_2014-12-27_08-00-05-.jpg
"Survivalcraft_2014-12-27_08-00-05-.jpg")The numbers given here were
done on two devices. It appears that other devices and perhaps later
game versions may have slightly different results. For example, before
spawn limit was equal to 28 creatures.

You can only spawn up to 34 (in 2.2 PC version) animals, if none of them
despawns due to a long distance from the player. 35th attempt gives you
the "Too Many Creatures" warning. You can go away and spawn more
creatures as long as the number of still not despawned creatures is less
than 34.

Interesting fact: every player is a creature. 34 creatures + 1 player =
35 creatures — a real forced spawning limitation.

If you try to spawn too many animals in a small place, they will simply
die instantly from being squeezed.

### How to spawn more than 34 creatures?

Some users report that the game lags when this is done. Perhaps more a
powerful device would not lag as easily.

#### Method 1

1.  Build an automatic egg dispenser.
2.  Fill it with spawn eggs.
3.  Set the maximum delay.
4.  Turn on the switch.
5.  Fly about 55 blocks to the side.
6.  Wait until the eggs run out.
7.  Come back.

#### Method 2

[Edit the Project file](Hacking_the_Project_file "wikilink").

#### Method 3

1.  Go away about 60 blocks from one bunch of creatures.
2.  Spawn another bunch of creatures at a distance of about 40 blocks
    from the first.

#### Method 4

You could try to force more animals into a tighter area by corralling
these to join the others. They will strongly resist. It is extremely
difficult and time consuming. 

## Automatic despawn associated with a long distance from the player

If you are in more than 52 blocks from any creature, it despawns and its
data move to the spawns data in chunks
('<Values Name="Spawn"><Values Name="Chunks">...'). It only stores data
such as the name of the creature, its coordinates and the boolean value
'ConstantSpawn', so if it spawn again, it will have full health\!

A creature is stored in spawns data. When a camera is moved within 40
blocks to a middle of a chunk, creatures spawn again and their data
moves to 'Entities'. A creature can be anywhere in the chunk, so it
spawns about 40 ± 11 blocks from the player.

## Automatic removal of animals from distant chunks

Certain chunks' data ('<Values Name="Spawn"><Values Name="Chunks">...')
deletes forever, if the character is too far away from them for 64
in-game days = 21.(3) real hours. To prevent this, you have to visit the
chunk, where your animals are stored. The time of the last visit updates
every 5 seconds and only for chunks within **8** blocks square around
players. An experiment was conducted proving that spawning of an animal
(when the distance is less than 40 blocks) can occur without updating
the time. Thus, if an animal despawns again in the chunk without an
updated visit time, it may disappear, although you do not expect it.

## Related Pages 

  - [Animals](../Bestiary/Creatures.md "wikilink")
  - [Animal Behaviors](Animal's_Behavior_list "wikilink")
  - [Cattle Farming](Cattle_Farming "wikilink")

[Category:Tips and Guides](Category:Tips_and_Guides "wikilink")
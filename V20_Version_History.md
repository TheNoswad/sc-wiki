---
title: V20_Version_History
description: 
published: true
date: 2025-10-13T00:22:29.184Z
tags: 
editor: markdown
dateCreated: 2025-10-13T00:22:24.904Z
---

For the official update list, see
[HERE](https://kaalus.wordpress.com/updates-history/) on the creator's
blog.

## Version 2.0 ("new game")

(Initial Release, Released in December 10, 2016)

  - Added furniture
  - Added multi-state furniture & connected multi-state furniture
  - Added furniture switches and buttons
  - Added furniture packs support to game and community content
  - Added hammer
  - Added push, pull & strict pistons
  - Added sea urchins
  - Added sea stars
  - Added kelp
  - Added sea grass
  - Fixed rendering bug with bow string on iOS
  - Added incendiary kegs
  - Added incendiary bombs
  - Worked around Kindle Fire 1 crash bug due to buggy shaders
    implementation
  - Changed lighting system to use uniform lighting for all block types
  - Accurate corner shading on stairs, slabs and furniture
  - Fixed block textures orientation on many block types
  - Added bisons
  - Added player stats
  - Added display of cause of death
  - Changed old clothing colors
  - Changed default world names
  - Changed door textures to better looking
  - Make saplings grow near water even if temperature or humidity is not
    quite right
  - Many more types of treasure items to be found in graves
  - Large dry bushes drop sticks
  - Added sea level adjustment
  - Made boat stronger and allowed player to spawn in boat
  - Changed clouds to better looking
  - Gradual death instead of sudden when out of bounds
  - Changed collapsing blocks to use the same underlying mechanism as
    pistons
  - Editing terrain blocks has priority over editing inventory items
  - Adjustable delay gates are now duplicable and stay in creative
    inventory when placed
  - Fixed a major pickables performance bug
  - Mounted electric elements can be mounted on non-transparent sides of
    transparent blocks (e.g. back of stairs)
  - Added particles when magma burns snow/ice or grass
  - Improved target texture
  - Tweaked underwater visibility, colors and fog based on
    humidity/temperature
  - Water plants slow movement in water
  - Lightbulbs can be painted
  - Added colored wires
  - Made colored wires not connect to other colors
  - New marble texture
  - New semiconductor texture
  - New minerals textures (sulfur, iron, coal, malachite, diamond,
    germanium)
  - Added semiconductor block
  - Fixed malfunctioning cattle drive and run away from noise behaviors
  - Fixed block picking with middle mouse button (Windows Store)
  - Fixed models turning heads when body is turning
  - Fixed XOR gate back texture
  - Fixed inventory bug when right-dragging single item (Windows Store)
  - Fixed font rendering offsets
  - Text layout accuracy improvements
  - Fixed glass sound
  - Crafting table no longer blocks fluids
  - Made clay paintable (good smooth material for furniture)
  - Added horizontal creative flight (Windows Store)
  - Creative mode digging/placement range increased from 5 to 8 blocks
  - Fixed malachite/iron help text bug
  - New UI backgrounds, panels, logos and icons
  - Decreased player height to 1.68m to look better besides furniture

## 2.1

(Released in July 26, 2017)

  - Added settings to disable supernatural creatures
  - Fixed inventory widgets dismissing with inventory button/e key
  - Adding Dropbox Api v2 support
  - DownloadFromLink dialog automatically deduces content type from link
  - Fixed and improved kill cause messages
  - Producing more pistons from the crafting recipe
  - Added food rot mechanics and rotten items (milk, meat, bird, fish,
    pumpkin, egg, dough, bread etc.)
  - Added 3d models for all food items
  - Added 3d models for all chunk items (coal chunks, stone chunk etc.)
  - Added creative mode reach setting
  - New food/health bar icons
  - Added Wire-Through Cobblestone
  - New MoveRose graphics, no more WASD letters
  - Added Split information label to InventorySlotWidget
  - Added support for having multiple players in the world
  - Added multiple view layouts (2-split horizontal/vertical, 3-split
    horizontal/vertical/even, 4-split)
  - Reduced complexity of sea urchin model (58 to 41 triangles)
  - Optimized bevelled rectangle drawing and removed panel textures
  - Human eye position tweaks to avoid clipping
  - Herding AI: chasers now break off and return to herd when too far
    away
  - Runaway AI: fixed spurious running away from a distant attacker
  - Made bison have cattle drive behaviour – drive herd of bison onto an
    animal you want to kill
  - Pilot AI tries to avoid other creatures
  - Added UI animations
  - Customizable colors palette and color names per world
  - Removed Disable Pathfinding setting, pathfinding is now always on as
    slow 1-core devices become rarer
  - Optimized InventorySlotWidget creation performance (cause of
    frequent hiccups)
  - Complete terrain engine rework to support multiple players in
    different locations using custom hashing
  - Negative world coordinates support
  - Moved default spawnpoint to around 0,0 to reduce float roundoff
    errors
  - Health replenished during sleep only when not starving
  - Cannot throw more often that once per 1.5 seconds in challenging to
    avoid machinegunning with rocks
  - GameMenuScreen turned to dialog to work for multiple players
  - New Survivalcraft 2 icon
  - Updated minerals textures
  - Cell door looks improved
  - Added menu music
  - Added gamepad support on Windows 8.1/Android/iOS
  - Sleeping system changes for multiple players. Time speeds up only if
    all players asleep/dead.
  - Biome size setting added
  - Larger default biome size
  - Much larger and more crazy mountains
  - Mountain peaks made more rocky
  - Added rivers
  - Added support for island generation with configurable size
  - Model rendering optimizations
  - Reduced minerals frequency
  - Generally more loot from animals
  - Reduced egg laying frequency of flightless birds
  - Movement controls default to touchpads on new installations (instead
    of directional buttons)
  - Piston duplication bug fixed
  - New framerate limiter (vsync based)
  - Added overhead player name display
  - Added possibility to flip screen upside down
  - Added female players support with sound, female players are weaker
    but faster and need less food
  - Added 4 male and 4 female players
  - Different default clothing for all player variants
  - Increased whistle summoning range and maximum pathfinding steps
  - Temperature is lower at night
  - Cows/bulls textures changed to better match other animals
  - Old clothing textures changed
  - Added brown instead of yellow by default
  - Increased attack resilience of most creatures
  - Wolves/bears/piranhas/hyenas/coyotes etc. drop rotten meat/rotten
    fish
  - Improved leather jerkin texture
  - Added Bullshark/Tigershark
  - Wildboar texture improvement
  - Sneak movement is slower
  - Added player levels
  - Replayed VitalStats panel with new display that shows how
    level/sickness etc. affects all abilities
  - Added collectable experience orbs
  - Dragging items on top of controls/buttons to drop them works
  - Added more players stats
  - Tweaked creature spawn ratios to have more dangerous animals
  - Added leopards
  - Added jaguars
  - Made tigers bigger, stronger
  - Added experience to graves
  - Fixed broken graves treasure generation
  - Spikes injure creatures every second, not continuously
  - Added sickness from food poisoning
  - Added puking
  - Cannot eat the same food all the time
  - LeftClick+Shift / A+LeftTrigger auto-move items to best inventory
    slot
  - Added pumpkin soup/rotten pumpkin soup
  - Added flu from cold
  - Added coughing attacks/sneezing
  - Fixed Survivalcraft malfunctioning in South Africa due to wrong
    culture handling
  - Increased lightning rate and made more random
  - Default players now have names: Walter, Basil, Geoffrey, Zachary,
    Doris, Mabel, Ada and Shirley.
  - Allowing longer visibility range: 320 blocks
  - iOS 7.0 now required due to gamepad support. iPod Touch 4G no longer
    supported (death to 256MB of RAM\!)
  - Fixed aiming circle offset for left-handed setup
  - Added help items for sickness, flu
  - Fixed model orientation when walking sideways/backwards
  - Campfires burn for longer and produce more heat
  - Increased campfire animals avoidance range
  - Animal spawning tweaked heavily to work with multiple players
  - Player requires level 2 to use diamond tools/weapons/armor
  - Players made slower, only speed up on gaining experience/wearing
    shoes
  - Added gamepad help dialog
  - Fixed and overhauled environment temperature system
  - Increased musket and crossbow strength/durability
  - Added one-led blocks
  - Increased large and medium keg explosion power
  - Added rot period display in block information
  - Improved zebra texture
  - Added bestiary with animals parameters displayed
  - Cotton clothes give 10% protection (absorb 10% of attack damage)
  - Running backwards made slower
  - Improved donkey texture
  - Added Multicolored LEDs
  - Increased precipitation particle system range when visibility range
    is large
  - Added iron ore chunks that need to be smelted instead of iron ore
    blocks
  - Added germanium ore chunks that need to be smelted instead of
    germanium ore blocks
  - Added death records to player stats

## 2.2

(Released in December 15, 2019)

  - Terrain height is doubled to 256 blocks
  - Visual glitches when too many complex blocks exist in one place are
    fixed
  - Increased performance of terrain geometry generation
  - Increased probability of saplings growing into trees
  - Added Mimosa trees
  - Improved tree generation patterns
  - Improved iron and copper textures
  - Increased probability of finding loot in graves
  - Removed unrealistic wooden and stone tools
  - Added new universal stone axe
  - Added wooden club
  - Added stone club
  - Slightly reduced throwing, bow and crossbow shooting speed
  - Projectiles stay in the world for longer
  - Bomb crafting recipe produces 4 bombs
  - Reduced experience gained from digging minerals
  - Fog only works horizontally (to be able to see ground from tops of
    the mountains)
  - Terrain generation overhaul: different mountains, more intermediate
    areas and many more
  - Increased torch light to 15
  - New lighting model: lightsources remove shadow, less edge shadowing
  - Added terrain textures mipmapping to reduce shimmering (optional –
    slows down the game by a few %)
  - Fixed lighting bug when only one piece of furniture was present in
    the world
  - Reduced Piranha attack strength
  - Biome size on islands is smaller to have more varied terrain
  - Made forests have more logs
  - Temperature calculation takes altitude into account
  - Colors of grass and other blocks take altitude into account
  - Added ice on tops of the mountains
  - Ice does not turn into water when harvested high up
  - Made some shy animals avoid player more
  - Reduced amount of spawned cats
  - Food takes longer to rot
  - It takes longer to get flu when being cold
  - Rotten food turns into compost
  - Fixed odd minus sign in fonts
  - Added damage value display after hitting a creature
  - Added new items category: Weapons
  - Increased health of larger animals
  - Increased damage dealt by arrows, bolts and bullets
  - Rain drops generate particles when striking ground or water
  - Snoflakes stay on the ground for a while
  - Added starting location difficulty option: Easy, Medium and Hard
  - Walking backwards speed reduced to 60% of normal
  - Reduced player food requirement by 20%
  - Reduced probability of predators attacking other animals
  - Tweaked weapon hit probabilities
  - When hitting a creature, sometimes there is no pushback effect
  - Increased number of inventory slots to 7 (up to 10 in creative)
  - Changed limestone and basalt textures
  - Made bears smaller, more realistic, they now fit in 1-wide space.
  - Improved player/creature ice slipping animation
  - Made polar bears have good traction on ice
  - Sneezing, coughing, puking will make noise and scare off birds
  - Added option to disable player-on-player attacks
  - Made block highlight of other players invisible
  - Added flat island mode
  - Added option to have rough shores in flat terrain modes
  - Improved sights texture visibility on snow
  - Improved terrain drawing at large distances from world origin
  - Improved clay texture
  - Brightened up wood and leaves textures
  - Iron trapdoor can no longer be used as furnace fuel
  - Made creative flying faster by 33%
  - Fish wag tail when attacking
  - Fixed eat pickable behaviour of creatures
  - Added Great White Sharks
  - Copper recipes require level 2 to craft
  - Iron recipes require level 3 to craft
  - Diamond recipes require level 4 to craft
  - Reduced amount of sharks, barracudas and piranhas.
  - Made boat stronger
  - Improved sharks models
  - Made wooden and stone arrows less accurate than metal arrows
  - In challenging/cruel/adventure player cannot place blocks if not
    standing on something
  - Made leaves drop sticks 15% of the time
  - Player can swim for longer before drowning
  - Crafting ladders produces 4 ladders instead of 2

## See also

  - <span lang="EN-GB" style="mso-ansi-language:EN-GB">[Survival Craft
    Version 2.0 Update
    Review](:File:SURVIVAL_CRAFT_2.0_UPDATE_REVIEW_and_Gameplay "wikilink")</span>

<!-- end list -->

  - <span lang="EN-GB" style="mso-ansi-language:EN-GB">[This is
    SurvivalCraft 2](:File:Survivalcraft_2 "wikilink")</span>

<!-- end list -->

  - <span lang="EN-GB" style="mso-ansi-language:EN-GB">[This is
    SurvivalCraft 2 Day One (free
    version)](:File:Survivalcraft_2_Day_One_\(free_version\) "wikilink")</span>

<span lang="EN-GB" style="mso-ansi-language:EN-GB">You can also find
videos focussed on one specific aspect of a version update like</span>

  - <span lang="EN-GB" style="mso-ansi-language:EN-GB">[Pistons](:File:Pistons "wikilink")</span>

<!-- end list -->

  - <span lang="EN-GB" style="mso-ansi-language:EN-GB">[Incendiary
    Explosives](:File:Incendiary_Explosives "wikilink")</span>

<!-- end list -->

  - <span lang="EN-GB" style="mso-ansi-language:EN-GB">[Furniture Part
    3](:File:Survivalcraft_Furniture_Part_3 "wikilink")</span>

<!-- end list -->

  - <span lang="EN-GB" style="mso-ansi-language:EN-GB">[Furniture Part
    2](:File:Furniture_Part_2 "wikilink")</span>

<!-- end list -->

  - <span lang="EN-GB" style="mso-ansi-language:EN-GB">[Furniture Part
    1](:File:Furniture_Part_1 "wikilink")</span>

__NOTOC__ __NOEDITSECTION__

[es:Historial de versiones](es:Historial_de_versiones "wikilink")

[Category:Tips and Guides](Category:Tips_and_Guides "wikilink")
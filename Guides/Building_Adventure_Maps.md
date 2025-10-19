---
title: Building_Adventure_Maps
description: 
published: true
date: 2025-10-12T23:36:17.632Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:36:13.569Z
---

An adventure map is made in creative mode and saved as an Adventure map
to play. See [adventure gamemode](adventure_Gamemode "wikilink"). 

This article helps you with more technical tips when building the
world. 

## Setting up Initial Conditions 

When a world is switched to adventure mode, the world is 'frozen' at
that point. That's how it will start up when the player begins to play,
or resets the adventure. You need to pay close attention to the entire
situation in the world around the character.

One common mistake map makers do is to forget to set a respawn point.
Adventure maps can have two start points. The primary one is the initial
start point, or the reset point. The second is a respawn point. This is
the sleep point and is the same as when in Challenging or Cruel modes.
You can set up the Adventure map so the player cannot respawn, he always
has to restart from the beginning. This is best for smaller maps. If you
do let them respawn, you need to sleep where you want the first one to
be. Usually this should be the same as the reset point. If there is no
place to sleep safely, you will have to build a temporary shelter to
sleep one night in. Once you wake, the shelter can be removed. 

### **Decide how you want the world to be when the player begins the adventure. **

There are environmental and character conditions you may wish to have
set up a certain way at startup. 

#### Environmental Conditions :

**What time of day should the character start in?** It's easiest to
start them off at dawn. Then you just sleep right before changing to
Adventure. If you want them to start off at sunset, you can advance the
time in Creative to sunset, then save and change it. 

**What DAY should it start on?** The main difference here is when the
wolves transform. Should they be werewolves on the first night? A random
new world always starts the day after the wolves transform (a full
moon). This way, the player has a chance to build up some resources
before the weres appear again. You may want to adopt the same principle.
Realize that the nights will be brighter according to the moon's phase,
as well.

To do this, you could have a trapped wolf nearby. Just make a 1x2 pit, 2
deep and spawn a wolf in it. Stay in Creative and stay near the wolf.
Advance time until sunset. Wait a minute and see if it changes. If not,
advance time until the next sunset. Repeat until the wolf transforms.
Kill the wolf, fill the pit, make any other final preparations then
sleep until dawn and save the game. 

Another way to check the date is to build a temporary calendar. Wolves
transform the evening before the days that are divisible by 4. I.e., the
nights of day 3, 7, B, and F. The moon is full on the nights of days 3
and B. The date is read from the 4th output of the Real Time Clock chip.
This is the best way to set the date if you want to have werewolves
appear the very first night, for instance. 

Or you could simply watch the moon's phases - assuming that the weather
cooperates.

**Should there be random beasts in the character's area when he
starts?** This is usually NOT a good idea, especially if he starts off
with nothing. Right before saving the game, fly around the reset point
and eliminate all the random spawns in the area. Remember that beasts
will spawn while the character sleeps. You may want to spend a minute
after waking, to clear out any newly spawned beasts, just before
saving. 

**Will the type of weather matter?** This is tough to set up. The
weather will be the same when the game is started, as it is when you
save it. But you can't tell what it will be afterwards, unless you
actually start the saved game and play it awhile. If it is unsuitable
for the character, you'll have to go back to Creative, keep weather on,
and wait until the conditions are right. Reset all the other startup
conditions (above) and try again. This can be very frustrating and is
usually just left to chance. But, it seems that the weather pattern is
set when the game is saved and will be the same every time the game is
restarted. 

Character Conditions:

**Should the character start off hurt, or hungry?** These are more
difficult, since he doesn't get hurt or hungry in Creative. You will
have to start it in Challenging mode and wait until he gets hungry. You
can use the suicide button to hurt the character before saving, to start
him off as already hurt. 

**What is he wearing? **

This usually depends on the storyline. Was he abandoned on the beach
with nothing or was he a part of a well-funded expedition? (See next
point.) 

**What is he carrying? **

This is basically the same as the previous item. You have to set these
up through a survival based mode first. One way is to start in Creative
 and placd a temporary chest near the character. Put everything you
want him to have in the chest. Put any clothes, food, weapons, etc. in
the chest. Quit and start it in Challenging. Gather everything from
inside the chest and put any clothing on. Quit and start it back in
Creative and destroy the chest. When the game starts in Adventure, he
will have everything you took from the chest. 

It's simpler to just place a chest near the start point but that doesn't
always fit the storyline well. 

## Death and the Respawn Point

If you are going to let the character respawn, make certain that you
have set the initial respawn point. Remember it is not the same as the
reset point. 

Some maps can take advantage of this, such as when imitating a
'transporter' or 'portal' effect. In this effect, the character dies to
activate the portal and the respawn is meant to be the 'destination' of
the transportation. 

Another map may want to have the character's death be the equivalent of
'being busted'. In this case, the respawn point would be the inside of a
jail cell. The player may have to set some 'code' or other change in the
world before they die. The change would then make it possible to escape
the jail but without it, they have to restart the adventure. 

## Wood, Tools and Crafting Tables

Many maps never allow the character to possess tools. Most tools can be
used to 'break' the game, so be very careful when you let them have any.

An axe can be used to make any other tool, for instance. All tools
require wood to make so if you deny them an axe, they cannot make other
tools unless you supply them wood. 

For similar reasons, a crafting table can be dangerous to the game
unless you make sure to never let them get wood. 

## Weapons 

In contrast to tools, weapons are often necessary in adventure maps.
They are often 'rewards' for solving some puzzle or found in hidden
chests. 

## Trapped Animals

Animals may be trapped behind doors or a falling wall, to be sprung on
the character at a set point in the adventure. Make sure the animal can
pass through the opening to get to the character. Many beasts cannot
pass through a single doorway even if the door is open. Larger beasts
require a 2 block space to move through. 

Remember that they will despawn if the character stays too far away for
too long. (What these limits are is still undetermined.) This applies
while you are building the world, too. If you are making a big world,
it's safest to have your traps and such set up, finish the map and then
populate the beasts just before saving, if this is feasible.

Also, animals are usually not overtly hostile during the day. If you
want them to be hostile, you may wish to set the game up so that the
character cannot enter the area during daytime. This is easiest when a
single entrance can be controlled with a light sensor. You can even have
a motion detector outside of the door to tell the player that it will
only open at night. Another simple method is simply to make the entire
game stay at midnight. This is set up in creative, before changing to
adventure mode.

A good alternative if you want to have animals in a specicif area, you
can use the [Dispenser](Dispenser "wikilink"), set them in Shoot Mode
and fill the Dispensers with [Creative Eggs](Creative_Eggs "wikilink").

## Common Mistakes 

### Respawn Point

Be sure to set the respawn point, if you are going to allow the player
to respawn. Never forget it's not the same as the reset point. 

### Placeable Blocks

Your planned adventure can be 'ruined' by inadvertently letting the
character gain placeable blocks. There are several ways this could
happen. 

Make sure there are no debris blocks still floating around, before you
set the game. It's easy to destroy a wall, for instance, then go to the
start point and quit the game, forgetting that there may be broken
blocks which haven't disappeared yet. Either make sure you pick up every
debris block or be sure to wait long enough for any to disappear.

If you have falling blocks in the map that are triggered by a trap door,
this can create debris that the character can pick up. The most common
way this happens is when the falling blocks break the trap door used to
trigger the fall. To avoid this, make sure all falling blocks will pass
right by the door. Another thing to watch is whether there's a breakable
block such as a torch under the block fall.

Explosions always create broken blocks unless very carefully designed.
If the explosion is meant to kill the character, make sure it will do so
under any circumstances the player may try. If it doesn't kill the
character, they will very likely be able to gather some placeable
blocks. 

Carefully design and the adventure so that either there are no broken
blocks or that when they do break, the debrised block falls safely out
of reach of the character. 

[Category:Tips and Guides](Category:Tips_and_Guides "wikilink")
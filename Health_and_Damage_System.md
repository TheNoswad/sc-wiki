---
title: Health_and_Damage_System
description: 
published: true
date: 2025-10-12T23:53:39.247Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:53:35.148Z
---

__NOTOC__ __NOEDITSECTION__

<table>
<thead>
<tr class="header">
<th><p>Health / Damage</p></th>
<th><p>Description / How to Calculate</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Health</p></td>
<td><ul>
<li>Each entity, player, animal, etc. has a health value.</li>
<li>Health is measured as a decimal value from 0 [dead] to 1 [full health]</li>
</ul></td>
</tr>
<tr class="even">
<td><p>Attack Resilience</p></td>
<td><ul>
<li>Injury = (Weapon Power) / (Attack Resilience)</li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Fire Resilience</p></td>
<td><ul>
<li>Injure to an entity per second = 1 / (Entities Fire Resilence)</li>
</ul></td>
</tr>
<tr class="even">
<td><p>Fall Resilience</p></td>
<td><ul>
<li>Minimal Speed (m/s) under which the animal/player/entity will recieve 0 damage from fall.</li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Stamina</p></td>
<td><ul>
<li>You can run 300 blocks [flat terrain] until you start to pant and slow down.</li>
<li>After 400 blocks, you are fully exhaused and move at 1/2 normal speed.</li>
<li>After 40 jumps in succession will get you exhausted to the point where you cannot jump amymore.</li>
<li>10 seconds of rest = full stamina</li>
</ul></td>
</tr>
<tr class="even">
<td><p>Sleep</p></td>
<td><ul>
<li>You can function 2 days without sleep.</li>
<li>After 2 days, you will collapse and lose consciousness.</li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Hunger</p></td>
<td><ul>
<li>Food does not restore health, it restores slowly over time.</li>
<li>You can function about 1 day without food.</li>
<li>You will slowly lose health after 2 days of no food.</li>
<li>Jumping, Fighting, etc. increases the need for food.</li>
<li>Once you are full, you cannot over eat.</li>
<li>If you are not well fed, health will not restore.</li>
</ul></td>
</tr>
<tr class="even">
<td><p>Freezing</p></td>
<td><ul>
<li>When in cold climates, you must wear heavy clothing or your body heat will drop.</li>
<li>Your clothes will lose all insulation when you are wet and you will get cold very fast. </li>
<li>Once your body heat drops too much, you will slowly lose health and your vision will become frosted.</li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Over Heating</p></td>
<td><ul>
<li>When too close to lava or fire for extended periods of time, your body heat will start to rise.</li>
<li>Once your body heat gets too high, you will slowly lose health and start to collapse.</li>
</ul></td>
</tr>
<tr class="even">
<td><p>Flu</p></td>
<td><ul>
<li></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Sickness</p></td>
<td><ul>
<li></li>
</ul></td>
</tr>
</tbody>
</table>

As of 1.26, time to regenerate health from 0 to 100% is as follows:

  - Harmless – 1 minute
  - Challenging (when hungry) – no regeneration
  - Challenging (normal) – 15 minutes
  - Challenging (when sleeping) – 10 minutes

Cruel mode is the same as Challenging. Health does not regenerate in
Adventure mode.

Remember that a full day/night cycle in SurvivalCraft is about 20
minutes long.

_____

Kaalus has recently fully explained combat damage calculations. Here is
his statement:

**Here's the way the game calculates attack damage:**

''Each animal has a life value that is between 0 and 1 (dead to full
health). The life value of player is displayed as hearts. A successful
attack reduces the life value of a creature by the following amount:

damage = attack power of attacker / resilience of target

A random factor of +/- 20% is added to every attack.

For example, a human male using bare hands has an attack power of 1. If
attacking a brown bear (resilience 60), the resulting damage will be:

damage = 1 / 60 = 0.0167

Not much. You need about 60 bare hands hits to kill the bear. On the
other hand if you’re wielding an iron machete (attack power 7), you just
need 8-9 hits.

If the defender is wearing armor, the armor takes the damage instead,
leaving body unharmed. After taking enough damage (indicated as Armor
Durability in Recipaedia), the armor will disintegrate.

“Soft” types of armor (like leather or fur) only absorb a part of the
damage, and the attack still partially damages the body. The percentage
of damage armor absorbs is displayed as Armor Protection (0 to 100%) in
Recipaeadia. Hard armors have it at 100%, leather at 50%, furs at 25%.
For 2.1 I am also making cotton clothes have 10% instead of 0% (so that
wearing clothes always helps a bit).''

## Related Pages 

  - [Body Temperature ](Body_Temperature "wikilink")
  - [Heating Your House](Heating_Your_House "wikilink")

[Category:Concepts](Category:Concepts "wikilink")
[Category:Organization](Category:Organization "wikilink")
[Category:Gamesystem](Category:Gamesystem "wikilink")
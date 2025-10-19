---
title: Piston_Vehicles
description: 
published: true
date: 2025-10-13T00:06:46.524Z
tags: 
editor: markdown
dateCreated: 2025-10-13T00:06:42.346Z
---

This article describes vehicles that may be built using pistons.

## Self-propelled Train

The first known invention of the self-propelled vehicle is shown
\[<https://kaalus.wordpress.com/2017/01/06/moving-contraption/>| on
Kaalus' blog\].

After experimenting with that design, I have discovered ways to improve
the design. The first one is to increase the rate of movement. You can
raise the extention of ALL the pistons to 8 blocks. The vertical piston
must also be slowed down to SLOW, to keep the proper timing.

In the blog, the OP claims the switch block must be made a certain way
but that isn't the case. Any full-sized (lever) furniture switch block
will work. The purpose of this block is simply to provide moving power
to the pistons.

Also, the original design will not effectively transport the character
as shown. It IS set up to have a train attached to the back but if you
just stand or crouch on it, you will slowly be dropped off the back.
This can be avoided by making the train using a couple special furniture
blocks. Make the bottom block like a furniture carpet block - one very
thin layer at the bottom. The layer above that is a 'microdot' block.
That is a single block shrunk into a 16-block space and moved into a
corner. See
\[<http://survivalcraft.lefora.com/topic/19407243/Invisible-wires>| this
page\] for more info. This lets the character pass through the block yet
it registers as a full block, to the pistons. The 'carpet' and
'microdot' blocks are pulled along by the pistons. At the very back,
behind these blocks, place two regular blocks.

With this combination, you can stand ON the 'carpet', inside the
'microdot' block, and the regular blocks will pull you along in the
train.

Another modification is to increase the size of the locomotive.
Additional horizontal pistons may be placed next to the interior switch
block. See the picture for an example.

<div style="overflow:hidden">

![Wide_piston_train_1.jpg](Wide_piston_train_1.jpg
"Wide_piston_train_1.jpg")

</div>

This shows both the wide train and the rider-friendly modifications. The
glass blocks let you watch the terrain go by while you're riding the
train. The space batween them is NOT empty - that's where the 'microdot'
blocks are. You can see the furniture carpet blocks under them. They're
the pale blue sheets.

The diamond-looking blocks are actually furniture switches.

Unfortunately, this cannot be built with a roof so you cannot sleep on
it, as someone suggested in the blog. It isn't a proper shelter.

Another option would be to replace the glass blocks and the rear blocks
with 'Invis glass blocks'. Then the only part of the train that's
visible is the 'carpet'. Of course, the locomotive section WILL be
visible but it will look like it's just pulling along a bit of carpet.
The character can still ride safely in back however.

### Notes

  - After some experimentation, a potential flaw has been discovered. In
    the wide version, the two sides seem to get slightly out of sync
    with the central section. The train still works but this can cause
    the character to fall out. The solution is simple, however. Just add
    one more layer to the very back of the train.

<!-- end list -->

  - Another issue regards the extended push distance modification. For
    some reason, the pistons do not retract smoothly. The train still
    works but it gives a very jerky ride.

<!-- end list -->

  - With the original 1-block push, the train moves about 24 blocks per
    minute.

<!-- end list -->

  - As with ALL electrics in SC, the train will NOT function if it is
    beyond the view range of the character.

<!-- end list -->

  - WARNING\! Using this train for extremely long distances will cause
    'file bloat'. As it moves, each chunk it passes through must be
    saved and not simply generated. The file will slowly grow and may
    eventually get too big for the system to handle.

[Category:Electricity](Category:Electricity "wikilink")
[Category:Machines](Category:Machines "wikilink")
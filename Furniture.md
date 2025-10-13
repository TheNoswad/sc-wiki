---
title: Furniture
description: 
published: true
date: 2025-10-12T23:50:41.364Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:50:36.964Z
---

## Description (from [Help](Recipaedia "wikilink"))

*Furniture blocks are sculpted from up to 16x16x16 smaller sub-blocks.
Sub-blocks within a single furniture block can be made of different
materials and painted to different colors. Through crafting, furniture
blocks can be combined, made interactive or made to work with
electricity. Furniture designs can be combined into packs, shared
between worlds and uploaded to Community Content.*

*To design and create furniture use the [hammer](Iron_Hammer "wikilink")
tool. You need to build the design from regular blocks in the world and
then use the hammer on the resulting structure to shrink it down.
Furniture design window will appear where you can tweak the design by
moving it, rotating it and changing resolution (between 2x2x2 and
16x16x16). Once you are happy with the design, you can commit it.*

*In [creative mode](Creative_Gamemode "wikilink"), the design will be
turned into a single furniture block, and the source blocks from which
the design was created will remain in the world. In [survival
modes](Game_modes "wikilink"), the design will be turned into several
copies of the furniture block (with number depending on resolution) and
the source blocks will be consumed. Furniture blocks can be placed in
the world in 4 orientations, similar to e.g. a furnace or a ladder.*

*Not every block can be used for furniture design. For example,
[dirt](dirt "wikilink") or [grass](grass "wikilink") are ignored by the
hammer tool. Allowed materials include: [planks](planks "wikilink"),
[granite](granite "wikilink"), [basalt](basalt "wikilink"),
[sand](sand "wikilink"), [clay](clay "wikilink"),
[cobblestone](cobblestone "wikilink"), [stone
bricks](Stone_Bricks "wikilink"), [sandstone](sandstone "wikilink"),
[marble](marble "wikilink"), [bricks](Brick_Wall "wikilink"),
[coal](Solid_Coal_Block "wikilink"),
[malachite](Malachite_Block "wikilink"),
[diamond](Solid_Diamond_Block "wikilink"),
[copper](Solid_Copper_Block "wikilink"),
[iron](Solid_Iron_Block "wikilink"), [glass](glass "wikilink"),
[carpet](carpet "wikilink"), [torches](Torch "wikilink"), [wicker
lamps](Wicker_Lamp "wikilink"), [water](water "wikilink"),
[magma](magma "wikilink"). Source blocks of the design can be painted or
dyed to make the design more colorful. Finished furniture can also be
painted, this will cover any colors of the source blocks.*

*Certain source blocks have special functions. For example a torch/lamp
block will cause the furniture to have a fire attached to it in the
place of the block. The design will also emit light.*

*You have to be careful when constructing furniture to avoid placing the
design on a base made of allowed material (for example sand). The hammer
tool will not be able to distinguish between the blocks you placed and
the base, and will try to incorporate base into design. This will likely
cause "design too large" error, because the maximum size of a design in
any dimension is 16 blocks.*

*Once the furniture block has been created, you can use crafting table
to combine it with other blocks in various ways. The following
combinations are possible:*

  - *Combine multiple pieces of furniture into one to create interactive
    furniture. Interactive furniture toggles between its constituing
    designs on click or on electric signal. You can create opening
    doors, switchable lights, raising platforms etc. Up to 9 pieces of
    furniture can be combined (max capacity of crafting table).*
  - *Combine exactly one furniture design with an electric button to
    create a custom button. The resulting furniture will act as a
    button.*
  - *Combine exactly two furniture designs with an electric switch to
    create a custom switch. The resulting furniture will act as a
    switch, with two furniture pieces acting as two states of the
    switch.*
  - *Combine multiple pieces of furniture with an electric wire to
    create connected interactive furniture. The furniture will work in
    the same way as interactive furniture, but toggling it will also
    toggle all neighboring pieces of connected interactive furniture.
    You can create multi-block toggleable structures, for example large
    doors.*

*In the furniture panel in creative inventory you can view and organize
your furniture designs. Create named furniture sets to categorize the
designs. The newly created designs are placed in "uncategorized" set,
which has a special function. Any design in this set, which does not
otherwise exist in the world (no items or placed blocks) will be
automatically recycled. Be careful and move valuable designs to named
furniture sets to avoid accidentally losing them. Each named furniture
set can be turned into a furniture pack and exported from the world. You
can later import it to other worlds or upload to Dropbox/SDcard and
share with others. Furniture packs can also be uploaded to community
content.*

*There are certain limitations to the furniture system:*

  - *A furniture block can be made from up to 16x16x16 sub-blocks.*
  - *The amount of geometry used for a single design cannot exceed 300
    triangles (too complex designs with many nooks and crannies are not
    possible). The game uses an intelligent tessellation algorithm that
    optimizes the geometry, so 300 triangles is plenty for even fairly
    complex designs, unless you really go over the top. To reduce number
    of triangles, you can for example reduce number of small details,
    reduce number of painted blocks and fill up any internal holes in
    the design.*
  - *You can only have up to 1024 unique furniture designs in the world.
    Every time you paint a furniture or combine it with others, you are
    creating new designs that count towards the total. Unused designs
    (that do not exist in the world either as items or blocks, and are
    in the "uncategorized" set in the inventory) are automatically
    recycled.*

-----

  - For more information on building furniture, see the [Advanced
    Furniture](Advanced_Furniture "wikilink") article page.

-----

## Crafting Process

This covers building static furniture using only solid blocks. It
describes the basic steps. More complex furniture is covered
[here](Advanced_Furniture "wikilink").

1.  Make a (larger) model of the piece. This cannot be bigger than 16
    blocks in any dimension. Use only the blocks and items in the list
    below. Make sure no unwanted block is touching your model. If you
    build in a created world, this includes the ground as well. That
    means the ground must be a non-usable block such as grass, or the
    model cannot touch the ground.
2.  When it's done, use the hammer on the model to open a UI window:

<div style="overflow:hidden">

![Edit_Furniture_window.png](Edit_Furniture_window.png
"Edit_Furniture_window.png")

</div>

There are two screens in this window, a control section on the left,
plus data at the top. The data tells you how complex the piece is, using
'triangles'. A piece must use no more than 300 triangles to define it.
This data tells you exactly how many triangles your piece uses.

  -
    The controls section has buttons for viewing the piece, and more.
    These will be explained below.

<!-- end list -->

  -
    You can make pieces from different sized models, up to 16x16x16.
    This is the maximum model size. If your model is smaller than that,
    you can 'shrink' it to make it smaller than a single block, by
    adjusting the control at the bottom. If you shrink a single block
    with this control at 16, then the created block will be 1/16 the
    length of a single block. If your model is 16 blocks big then you
    will not be able to adjust this control. The minimum size of the
    model is 2 blocks. You can make furniture using only 1 block but it
    will be shrunk to half its dimension.

<!-- end list -->

  -
    The left screen shows the piece from the view selected in the
    controls section. You can choose between TOP, FRONT and SIDE views
    using the top button in the controls. The triangles let you move the
    piece within the chosen model size and according to the view in this
    screen. The curved arrows rotate the piece, within the selected view
    as well.

<!-- end list -->

  -
    The right screen is a dynamic view so you can see the piece in 3-D.
    You can hold/drag on this section to rotate the view from any angle.

<!-- end list -->

  -
    At the top right of this window is a (...) button. This is used to
    name the piece you are creating. (You can also use it to rename an
    existing piece if you 'hammer' the existing piece.)

3\. When the piece is positioned and sized as needed, tap CREATE and the
UI goes away and the designer block falls from the hammer, and into your
inventory. The original model is NOT destroyed in this process if you
are in creative mode.

4\. After creating the piece, you should add it to a furniture pack.
Pieces that aren't assigned to a pack may be deleted by the game. See
the next section.

### Notes

  - You can only have up to 1024 furniture designs. If you try to sculpt
    furniture wen you have the maximum amount, a message apears saying
    "Too Many Different Furniture Designs".

<div style="overflow:hidden">

![Survivalcraft_2017-01-02_20-17-25.jpg](Survivalcraft_2017-01-02_20-17-25.jpg
"Survivalcraft_2017-01-02_20-17-25.jpg")

</div>

  - As stated in the recipaedia, the number of pieces you get is
    dependant on the 'resolution' of the design. You will get the number
    shown in this table:

| Res. | Amt. |
| ---- | ---- |
| 2    | 4    |
|      |      |

## Furniture Packs

Furniture pieces are organized into packs. Each pack can hold many
different pieces. You can have up to 45 packs loaded in the game. If you
try to create or import a furniture pack when you have the maximum
amount, a message apears saying "Too Many Furniture Sets".

<div style="overflow:hidden">

![TooManyFurnitureSets.png](TooManyFurnitureSets.png
"TooManyFurnitureSets.png")

</div>

To work with furniture packs, open the inventory window and choose
FURNITURE in the category tab.

<div style="overflow:hidden">

![Furniture_Category.png](Furniture_Category.png
"Furniture_Category.png")

</div>

There is always a pack called "Uncategorized". This is somewhat like the
trash can on a computer - any unused designs left in here long enough
will be deleted in time. When you delete a pack in this window all the
designs first go into this category. When you first make a new design,
it is 'stored' in here.

To add a newly made piece to an existing pack, select UNCATEGORIZED
'pack'. This will show you all the pieces that aren't in a pack. Scroll
down the list to find the pack you want to save the new design in,
WITHOUT selecting a different pack. Take each piece you want to save and
drag the piece from the right side into the furniture pack of your
choosing.

At the bottom of this panel is an ADD button to create a new furniture
set or pack. This button also lets you import furniture packs from
'content'. This content is stored in the game just like block textures
and character skins.

<div style="overflow:hidden">

![Add_Furniture_Set.jpg](Add_Furniture_Set.jpg
"Add_Furniture_Set.jpg")

</div>

You can do other operations to the furniture packs by selecting the pack
and tapping the (...) button:

<div style="overflow:hidden">

![Furniture_Pack_Actions.jpg](Furniture_Pack_Actions.jpg
"Furniture_Pack_Actions.jpg")

</div>

This lets you rename the selected pack, delete it from the game, move it
up or down in the list, or export it to 'content'. You must first save
your furniture pack to content if you wish to move it from one world to
another or to upload it to the Community Content. See [this
page](Uploading_and_Downloading "wikilink") for uploading details.

## Notes

  - You can make furniture that looks 'identical' to the original block
    by using 8 blocks in the model. The furniture is not quite exact
    because the texture pattern is somehow turned upside-down. (This has
    been corrected in the latest 2.1 version.)
  - Furniture does not automatically orient itself to match other
    similar blocks. For instance, normal planks will always run
    east-west no matter which way you are facing when you place them. A
    furniture block made to look like planks will run differently
    depending on which way you face when placing them.
  - Furniture of any construction is a heat blocker.
  - Any emitted light will be the same regardless of how many torches or
    lamps are used.
  - The axe is needed to break furniture in [Adventure
    Gamemode](Adventure_Gamemode "wikilink").
  - Furniture items may be used as fuel in the furnace and campfire.
  - Furniture will not get destroyed by arrows, bolts or musket balls,
    even if they are made of materials that will.
  - The properties in the infobox are all shared with every furniture
    regardless of the blocks used.
  - Naming furniture is done by clicking on the (...) in the top-right
    corner of the furniture editing UI. It is similar to renaming worlds
    from there.
  - You can rename furniture by clicking on it with a hammer and then
    renaming it from the (...) in the top-right corner. You can chose to
    rename the original or a modified copy.

## Useable Blocks List

  -
    Any paintable block in this list may be used in either its painted
    or natural versions.
    Partial blocks such as slabs cannot be used.

<!-- end list -->

  - [Basalt](Basalt "wikilink")
  - [Brick Block](Brick_Wall "wikilink")
  - [Carpet](Carpet "wikilink")
  - [Clay](Clay "wikilink")
  - [Coal Block](Solid_Coal_Block "wikilink")
  - [Cobblestone](Cobblestone "wikilink")
  - [Copper Block](Solid_Copper_Block "wikilink")
  - [Diamond Block](Solid_Diamond_Block "wikilink")
  - [Glass](Glass "wikilink")
  - [Granite](Granite "wikilink")
  - [Iron Block](Solid_Iron_Block "wikilink")
  - [Magma](Magma "wikilink")
  - [Malachite Block](Malachite_Block "wikilink")
  - [Marble](Marble "wikilink")
  - [Planks](Planks "wikilink")
  - [Sand](Sand "wikilink")
  - [Sandstone](Sandstone "wikilink")
  - [Stone Bricks](Stone_Bricks "wikilink")
  - [Water](Water "wikilink")

### Notes

  - Special care must be taken when including water or magma. There
    cannot be a flowing block or the hammer will reject the design. If
    the rest of the design does not create a 'container' for the fluid,
    one must be created to contain it. In this case you must use
    'ignored' blocks - usually dirt to block in the fluid. This way the
    fluid will not flow and the dirt will not be included in the final
    block.

## Useable Items List

  - [Torch](Torch "wikilink")
  - [Wicker Lamp](Wicker_Lamp "wikilink")
  - [Button](Button "wikilink")
  - [Switch](Switch "wikilink")

__NOEDITSECTION__

[Category:Concepts](Category:Concepts "wikilink")
[Category:Furniture](Category:Furniture "wikilink")
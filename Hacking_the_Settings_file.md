---
title: Hacking_the_Settings_file
description: 
published: true
date: 2025-10-12T23:53:22.222Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:53:18.326Z
---

The settings file for the game holds all the settings avilable in the
game. That includes screen resolution to gamepad dead zone and so much
more\! But what you may not know is that you can hack the game files to
get some insane stuff such as crazy fps and better lighting if you feel
like 10 is just not enough. But most imporantly it holds the visibility
range too, if you change your current visibility range to something
bigger.

# Visibility Range

For example, your visibility range may be 320 blocks, the current
maximum and you change that to 1024 blocks (8GB and a computer is
required) then you will get a little more than 3x the current maximum
3.2x to be exact. This can work with any number, even odd ones, although
I dont reccomend setting the visibility over 1024 because it can crash.
2048 blocks can be loaded on a flat terrain but the terrain is very
weird very far away so limit it to 1024. If you have a high-end GPU (GTX
970-980Ti, 1070-1080Ti), it should crazy fast\! If you have a mid range
gpu (GTX 950-960, 1050Ti-1060 6GB), then set it to 512 blocks, though
you shouldn't lag just after 768 blocks.

## How to do it?

1.  Open up your windows file explorer.
2.  Type this in the upper bar left to the search bar and type in:
    user\\appdata.
3.  Click local then find packages.
4.  Find 20961CandyRufusGames.Survivalcraft2_c7jxg4av36ap6 and click on
    it.
5.  Click on LocalState file, then click on Settings.xml.
6.  If it asks you what you want to open it with click notepad and say
    to always open it with notepad.
7.  Find <Setting Name="VisibilityRange" Value="320" /> and change it to
    anything. The maximum recommendation is 1024 blocks aka 64 chunks.
8.  Have fun\!

You now know how to hack the settings.xml file. From now on it should
appear in quick access

## How it looks\!

Here is how 1024 block visbility range looks like in the settings: 

<div style="overflow:hidden">

![Bandicam_2017-07-28_20-08-01-053.png](Bandicam_2017-07-28_20-08-01-053.png
"Bandicam_2017-07-28_20-08-01-053.png")

</div>

Here is the beauty of a 1024 block render distance: 

<div style="overflow:hidden">

![Viewdist1024.jpg](Viewdist1024.jpg "Viewdist1024.jpg")

</div>

# Notes

\-This has only been demonstrated on a windows machine (not portable).

\-It has yet to be attempted on an android and is not possible on iOS
systems because the settings files are not available to the user.

\-If this is possible on mobile, don't set it above 512 blocks\! 512
blocks and above are for computers ONLY, or if you want to crash your
phone.

\-Blocks dissapear after 856 blocks, and there is no way of changing
this. Terrain generated after 856 blocks will appear white.

# Related Pages

  - [Visibility Range](Visibility_Range "wikilink")
  - [Hacking the Project file](Hacking_the_Project_file "wikilink")

[Category:Tips and Guides](Category:Tips_and_Guides "wikilink")
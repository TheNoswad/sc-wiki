---
title: Files
description: 
published: true
date: 2025-10-12T23:48:42.667Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:48:38.681Z
---

This article describes the several files used by SurvivalCraft as well
as some files outside of the game but available from the developer.

## Description

SurvivalCraft uses two files to customize the game. These are the
texture file (default.scbtex) and the skin file (default.scskin). They
can be changed by importing new textures or skins into the game. There
are also external ways to add them. See below.

There are also a couple files used by the game that are not generally
modifiable. These are the chunks.dat (chunks32.dat for 1.29-up) and
project.xml files. These files are technical and should never be altered
by the user.

Some files are available from Kaalus' blog, for information purposes.
This includes the default images, blocks data and items icons. These may
not be updated for each version.

## Customizing Files

### Block Textures

[Block textures](../Recipaedia/Construction/Mechanics/Block_Textures.md "wikilink"), or texture packs allow the
terrain looks to be changed. Many items can also be altered through this
image. Copy this and edit it on your paint software\! Read more here,
<https://kaalus.files.wordpress.com/2017/06/blocks.png>.

### Skins

[Skins](Skins "wikilink") are what you can edit to look like anyone or
thing you want, you can do anything as long as you stay in the lines.
Edit to change the way your player looks\! You cannot change his shape,
learn more about it at the link above. ![centre](Human.png "centre")

## Reference Files

The blocks data and icons files are compressed and combined to make it
simpler to download.

### Blocks Data

This file is provided by CandyRufusGames. It is primarily intended for
map makers and gives various information regarding every block and item
found in SurvivalCraft.

### Icons

This file is provided by CandyRufusGames. It is primarily intended for
use by wikis and others to help in creating reference documents. An icon
is provided for each block and item.

### Chunks.dat file format

This (outdated) file describes how the world data file, or 'chunks' is
formatted. Modifying this file will affect any previously altered world
chunk. Any terrain (chunk) that was not modified will not be represented
in this file. Such chunks are generated during world terrain generation.

### Default Blocks Texture

This is the built-in texture image. It is provided for a base to start
with, so you can modify it for your needs.

### Default Player Skin

This is the built-in player skin. It is provided for a base to start
with, so you can modify it for your needs.

## Internal Files

This section is only for those who are capable of understanding software
code. Please do not do this without backing up your original world
first\!

### Accessing internal files

To access the internal files, you might be able to use the following
procedure. Note that it might be different on other systems. This was
written for an Android based system.

1.  Back up your world, either to SD card or the 'cloud'. The world file
    is actually several files, compressed into one.
2.  Change the name of the world file from XXXX.scworld to XXXX.zip.
3.  Open the zip file. There are many ways to do this. This author uses
    a file browser named "XPLORE.app" which makes this step simple. I
    just have to close the enclosing folder, open it again, and tap on
    the zip file. This opens it as if it were simply another folder.
4.  There should be 3 files and a folder inside this. The files are the
    Chunks32.dat file, the Project.xml file and a backup file,
    Project.bak. The folder will be named *EmbeddedContent*. This holds
    any downloaded skin or texture files.
5.  Copy any file you wish to modify, into another folder to work with
    them.

\--- Once you have made all chang

[Category:Help Pages](Category:Help_Pages "wikilink")
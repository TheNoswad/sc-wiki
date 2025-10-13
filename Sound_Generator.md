---
title: Sound_Generator
description: 
published: true
date: 2025-10-13T00:14:48.992Z
tags: 
editor: markdown
dateCreated: 2025-10-13T00:14:44.837Z
---

__NOEDITSECTION__

Creates various sounds played through the speakers that can be
controlled electrically.

## Description (From [Recipaedia](Recipaedia "wikilink"))

*Electric sound generator. Takes 4 inputs: Pitch (left), Octave (right),
Volume (top) and Tone (bottom). All of these inputs are analog. The
pitch ranges from C note (value of 0V) to D note in the next octave
(value of 1.4V). 1.5V at pitch input means pause, no sound is played.
The octave input can be used to shift the pitch by up to two octaves.
The volume input sets the volume of played sound, with 0V being muted
and 1.5V being the loudest. The actual sound is played whenever tone
input goes from zero to non-zero. The value supplied to the tone input
when it goes from zero to non-zero determines which instrument should be
played: 0.1=Bell, 0.2=Organ, 0.3=Ping, 0.4=String, 0.5=Trumpet,
0.6=Voice, 0.7=Piano, 0.8=PianoSustain, 0.9=Drums. With drums, pitch
input determines one of 10 drums: 0.0=Snare, 0.1=BassDrum,
0.2=ClosedHighHat, 0.3=PedalHighHat, 0.4=OpenHighHat, 0.5=LowTom,
0.6=HighTom, 0.7=Crash, 0.8=Ride, 0.9=Handclap. Some animals, especially
birds, are afraid of the loud sounds. This element can be placed on any
surface and rotated to desired orientation.*

## Crafting

It requires 1 [iron ingot](Iron_Ingot "wikilink"), 2 [copper
ingots](Copper_Ingot "wikilink") and 4 [germanium
crystals](Germanium_Crystals "wikilink") to craft Sound Generator.

You get 4 generator 'chips'. ![Sound_Generator.png](Sound_Generator.png
"Sound_Generator.png")

## Hooking it Up

### Connections

There are 4 inputs, one on each edge and all of them are analog signals.
They must be supplied by a device with analog outputs such as a
[DAC](Digital_to_Analog_Converter "wikilink") or a [memory
bank](Memory_Bank "wikilink").

The TONE input needs more attention. It has to go to '0 then to the
value wanted. One way to do this is to use a memory bank as a gate. It
requires programming but is compact. ![Sound_pins.jpg](Sound_pins.jpg
"Sound_pins.jpg")Another is to use an AND gate. One input to this gate
is the analog value and the other is a digital 'enable' signal. (See
[Using Analog Signals](Using_Analog_Signals "wikilink") for more details
on this technique.)

### Operation

The **TONE** input doubles as the 'GO' switch. It must be held at '0'
until the sound is to be played.

The sound begins only when this input *changes from '0'\!*  Then it will
play a sound with the voice specified by what that value is.
<see table below> The sound will last only about 1 second and fades
away. If the tone input goes to '0' and then ''changes from '0'  ''again
before the first note fades, then the second note will be played and the
first note will be cut short.

The **PITCH** input controls the frequency of the sound and spans one
octave. The pitch equals the "western scale" where C = '0', C\# = '1', D
= '2' . . . C2 = 'C'.  \<lol - C is C\>  Then C2\# = 'D' and D2 = 'E' 
If the pitch value is 'F' (1.5V) the generator plays a silent note or
'pause'. The frequencies played are very close to standard reference
pitches. You can play along with your real piano and they should be in
tune\! If this input is not connected, it plays the lowest pitch.

The **OCTAVE** input shifts the frequency of the sound down an octave or
two according to its value. However it can only be changed by 2 octaves
(or the values '0' through '2'). Any value over '2' is played as the
highest pitch. If this input is not connected, it acts as if it were a
'2'.

The **VOLUME** input controls -of course- the volume of the sound. When
it is '0' the ouput is muted and an 'F' is full volume output. If this
input is not connected, the volume will be at maximum.

### TONE  (or Voice) chart

|   |                |
| - | -------------- |
| 0 | **ready mode** |
| 1 | Bell           |
| 2 | Organ          |
| 3 | Ping           |
| 4 | Strings        |
| 5 | Trumpet        |
| 6 | Vocal "doo"    |
| 7 | Piano          |
| 8 | Piano Sustain  |
| 9 | Drums          |

For the drum channel, the tone input sets the drum sound as follows:

|   |                 |
| - | --------------- |
| 0 | Snare           |
| 1 | Bass Drum       |
| 2 | Closed High Hat |
| 3 | Pedal High Hat  |
| 4 | Open High Hat   |
| 5 | Low Tom         |
| 6 | High Tom        |
| 7 | Crash           |
| 8 | Ride            |
| 9 | Handclap        |

## Uses

  - It can be used to scare some animals away.

<!-- end list -->

  - With a lot of other circuitry, it can play music.

<!-- end list -->

  - Hook it up to a RTC and it can chime different tones at different
    times.

<!-- end list -->

  - Connected to other circuitry, it can play warning tones in adventure
    maps.

## Notes

  - The sound generator was added in version 1.23.

<!-- end list -->

  - The wording in the description and chip label may unfortunately be
    confusing. The term 'note' gets multiple meanings in music theory.
    It properly describes the totality of one continuous sound,
    including the pitch, octave, tonal quality and duration. However it
    is often used to describe just the frequency (pitch) of a sound. The
    term 'tone' is often misused as well, also often used in place of
    pitch. The pitch of a note is actually the combined effect of the
    'pitch' plus octave.

<!-- end list -->

  - The actual effect on animals is still unknown. Whether animals
    nearer to the device or the player are affected more or not is one
    outstanding question. When these issues are known, the information
    will be provided...
  - As of 1.29, Sound generators produce small notes when they produce
    sounds. The piano sustain and drum channels were also added.

[Category:Electricity](Category:Electricity "wikilink")
[Category:Electric Chip](Category:Electric_Chip "wikilink")
[Category:Electrics](Category:Electrics "wikilink")
[Category:Crafted](Category:Crafted "wikilink")
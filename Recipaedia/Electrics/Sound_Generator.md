---
title: Sound Generator
description: The sound generator is an electrical component that can be used to play audible sounds.
published: true
date: 2025-10-23T01:58:39.162Z
tags: 
editor: markdown
dateCreated: 2025-10-13T00:14:44.837Z
---

## Description (from [Recipaedia](Recipaedia))

> Electric sound generator. Takes 4 inputs: pitch (left), octave (right), volume (top) and tone (bottom). All of these inputs are analog. The pitch ranges from C note (value of 0V) to D note in the next octave (value of 1.4V). 1.5V at pitch input means pause, no sound is played. The octave input can be used to shift the pitch by up to two octaves. The volume input sets the volume of played sound, with 0V being muted and 1.5V being the loudest. The actual sound is played whenever tone input goes from zero to non-zero. The value supplied to the tone input when it goes from zero to non-zero determines which instrument should be played: 0.1=Bell, 0.2=Organ, 0.3=Ping, 0.4=String, 0.5=Trumpet, 0.6=Voice, 0.7=Piano, 0.8=PianoSustain, 0.9=Drums, 1.0=Bass. With drums, pitch input determines one of 10 drums: 0.0=Snare, 0.1=BassDrum, 0.2=ClosedHiHat, 0.3=PedalHiHat, 0.4=OpenHiHat, 0.5=LowTom, 0.6=HighTom, 0.7=Crash, 0.8=Ride, 0.9=HandClap. Some animals, especially birds, are afraid of the loud sounds. This element can be placed on any surface and rotated to desired orientation.

## Crafting

**Ingredients:**
* 1 [Iron Ingot](/Recipaedia/Items/Iron_Ingot)
* 2 [Copper Ingots](/Recipaedia/Items/Copper_Ingot)
* 4 [Germanium Crystals](/Recipaedia/Minerals/Germanium_Crystal)

**Yield:** 4 sound generator items

![sound_generator_recipe.webp](/media/recipes/sound_generator_recipe_1.png)

## Connections

The sound generator has four primary connections, located around all four sides of the component. These are the **pitch**, **volume**, **octave**, and **tone** inputs. They must be supplied by a device with analog-based outputs, such as a [Switch](Switch), [Button](Button), [Digital to Analog Converter](Digital_to_Analog_Converter), or [Memory Bank](/Recipaedia/Electrics/Memory_Bank). There is also a secondary tone connection, which can be accessed by placing the Sound Generator on a wire-through-block.

### Tone

The tone connection doubles as the trigger and instrument input. The actual audible sound is only played when the tone input changes from a value of zero to a value that isn't zero. This is also known as the *rising edge* or *null value*. The duration of any given sound will last for approximately 1 second and fade out quickly. If the tone input reverts to zero and then back to non-zero before the first note fades, then the second note will be played and the first note will be cut short.
![sound_pins.webp](/media/sound_generator/sound_pins.webp)


### Instrument

The analog value supplied to the tone input determines the instrument type used when playing a sound. As of the 2.4 update, there are a total of ten different instruments:

| Decimal Value | Hex Value | Instrument    |
| ------------- | --------- | ------------- |
| 0.1           | 1         | Bell          |
| 0.2           | 2         | Organ         |
| 0.3           | 3         | Ping          |
| 0.4           | 4         | Strings       |
| 0.5           | 5         | Trumpet       |
| 0.6           | 6         | Voice         |
| 0.7           | 7, F      | Piano         |
| 0.8           | 8         | Piano Sustain |
| 0.9           | 9         | Drums         |
| 1.0           | A         | Bass          |

### Pitch

The pitch connection raises or lowers the pitch, or frequency, of the note being played. Think of a piano note scale (cCdDefFgGaAb), except instead of using only letters, a combination of numbers and letters are used (in hexadecimal notation). Value 0 is the lowest note (flat c), while value B is the highest (flat b). Values C, D, E are often irrelevant, as they play notes c, C, d but in the next octave. Value F acts as a mute; no sound will be played when the pitch is set to F.

### Octave

The octave connection shifts the note range up or down by a matter of 12 notes. While there are only a maximum of four octaves, the number and relative range of supported octaves depends on the instrument. When a note is played outside of its supported octave range, it will always play a note with the pitch of 0 in the highest octave, regardless of the supplied pitch or octave.

The default octave value is set to 2 when no wire or component is connected. The full octave ranges of all instruments are listed below:

| Instrument    | Octave Range |
| ------------- | ------------ |
| Bell          | 0-3          |
| Organ         | 0-2          |
| Ping          | 0-3          |
| String        | 0-3          |
| Trumpet       | 0-3          |
| Voice         | 0-3          |
| Piano         | 0-3          |
| Piano Sustain | 0-3          |
| Drums         | N/A          |
| Bass          | 0-3          |

Depicted below are the octave ranges for all instruments in relation to a piano scale. It should be noted that the octaves ranges for the Ping and Voice instruments are shifted up by one octave (3, 4, 5, 6). You can cover a wider range of octaves (5 in this case) by combining similar sounding instruments together, such as the Piano and Ping or Bell and Voice.

![octave-range_1.webp](/media/sound_generator/octave-range_1.webp)
![octave-range_2.webp](/media/sound_generator/octave-range_2.webp)
![octave-range_3.webp](/media/sound_generator/octave-range_3.webp)

#### Drum Sounds

It should be noted that the drum instrument does not respond to octave. There are only ten total drum sounds, which are determined by the respective pitch values:

| Pitch | Drum            |
| ----- | --------------- |
| 0     | Snare           |
| 1     | Bass Drum       |
| 2     | Closed High-Hat |
| 3     | Pedal High-Hat  |
| 4     | Open High-Hat   |
| 5     | Low Tom         |
| 6     | High Tom        |
| 7     | Crash           |
| 8     | Ride            |
| 9     | Handclap        |

### Volume

The volume connection determines the number of blocks a sound generator can be heard from, relative to the player. A value of F is the highest possible volume, while a value of 1 is the lowest possible audible volume. A value of 0 completely mutes the sound generator.

The default volume value is set to F when no wire or component is connected.

## Potential Uses

* With a lot of additional circuitry, it can be used to play music. Popular music maps include [Music 45 Songs](https://www.youtube.com/watch?v=0WoFjP6DLDo) and various [Standalone Music Maps](https://www.youtube.com/playlist?list=PLGt3W-nliAhB-RMYCoj3F__uLCwytiwVj).
* Some animals are frightened by sounds, and can be used to deter them.
* Alarms or small multi-note jingles can be created when connected to other circuitry.
* Can be used to play audio (the ping instrument usually works best) in a button interface or control panel.
* Using a [Real Time Clock](Real_Time_Clock), it can be programmed to chime different tones at different times (almost like a Coo Coo-clock).

## Game Limitations

* The 'sustain' sound effect for the Sustained Piano cannot be cancelled or muted prematurely. It will always sustain every note played, regardless if the sound generator is muted after a note is played or a non-sustained note is played right afterwards. This is either a game limitation or simply an unintended issue.
* There is a soft limit for how many instruments can be used at a given time, which is around 5-6. You will know you have reached the limit when you can audibly hear notes being skipped/muted, even though a visual note is played. This phenomenon is especially noticeable with a primary melody or mid-range tracks. Not much is currently known about the specifics; this is only a real concern when working with sound generators on a mass-scale.

## History

| Version | Changes                                                                                                                                                                                                            |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1.23    | Added sound generator.                                                                                                                                                                                             |
| 1.29    | Sound generators now emit small colored notes when sounds are produced. Improved the piano instrument. Added Piano Sustain and Drum instruments. Sound generators are now able to be mounted on the floor/ceiling. |
| 2.4     | Octave ranges for the Bell, Ping, String, Trumpet, and Voice instruments were all increased by one. Fixed many invalid sounds for the Bell and Ping instruments. Added the Bass instrument.                        |


## Technical Information
| Property | Value |
|----------|-------|
| **Class Name** | SoundGeneratorBlock |
| **Display Name** | Sound Generator |
| **Category** | Electrics |
| **Display Order** | 250 |
| **Crafting ID** | soundgenerator |
| **Texture Slot** | 78 |
| **Is Collidable** | FALSE |
| **Is Placeable** | TRUE |
| **Is Digging Transparent** | FALSE |
| **Is Placement Transparent** | TRUE |
| **Is Interactive** | TRUE |
| **Is Editable** | FALSE |
| **Is Gatherable** | FALSE |
| **Is Fluid Blocker** | FALSE |
| **Is Transparent** | TRUE |
| **Max Stacking** | 40 |
| **Friction Factor** | 1 |
| **Density** | 3 |
| **Sound Material** | Stone |
| **Shovel Power** | 1 |
| **Quarry Power** | 1 |
| **Hack Power** | 1 |
| **Melee Power** | 1 |
| **Melee Hit Probability** | 1 |
| **Projectile Power** | 1 |
| **Tool Level Required** | -1 |
| **Durability** | -1 |
| **Dig Method** | Hack |
| **Dig Resilience** | 1 |
| **Explosion Resilience** | 5 |
| **Destruction Debris Scale** | 0.5 |

Would you like me to adjust which properties are included or change the formatting?

## Notes

* As of update 1.29, sound generators emit small visual colored notes when they produce sounds. The color of the note is determined by the respective pitch, while the visual style of note is simply random.
* Update 2.4 made a lot of improvements to the sound generator. Some sounds for certain instruments were adjusted, while others were completely changed (such as the ping instrument). More octaves were added to the majority of instruments, with the organ being the only instrument left untouched. The bass instrument was also added.
* As of update 2.4, there are a total of 439 unique sound generator sounds.
* The wording in the description and chip label may unfortunately be confusing. The term 'note' has multiple meanings in music theory. It properly describes the totality of one continuous sound, including the pitch, octave, tonal quality, and duration. However, it is often used to just describe the frequency, or pitch, of a sound. The term 'tone' is often misused as well, and is often used in place of pitch. The pitch of a note is actually the combined effect of the pitch plus its octave.
* The actual effect on scaring away animals is still unknown. Whether the relative distance of animals to the device or the player has any affect is currently still a mystery. More information will be provided, if it is discovered.
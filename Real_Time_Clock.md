---
title: Real_Time_Clock
description: 
published: true
date: 2025-10-13T00:09:05.019Z
tags: 
editor: markdown
dateCreated: 2025-10-13T00:09:00.842Z
---

__NOEDITSECTION__

The real time clock can be used as an in-game clock. It does not read in
Earthly minutes and seconds, but in "Survivalcraft world" time. You can
create a simple clock by using this block and [7-segment
displays](7-Segment_Display "wikilink"). It is possible to convert this
time into Earthly play time but is very complicated.

## Description   (From [Recipaedia](Recipaedia "wikilink") )

*A real time clock that provides an accurate and always up to date
readout of time. The clock value changes even if it's far away from the
player. Zero value of the clock is at the point when the game started.
You cannot reset the clock, it always tells the time since the game
started. The clock outputs time via 5 outputs, each of them 4-bit analog
signal. Sixteen least significant bits are on the four sides, and the
5th output (containing the most significant 4 bits) is on the back (you
must place the clock on a wire-through-block to access the 5th output).
The clock is set up so that it advances by exactly 4096 ticks each day.
That means each tick is about 0.3 seconds long and that 4th output
contains number of days since the game started. Combined value of
outputs 1, 2 and 3 contain time of day, to about 0.3 second accuracy.
4th output alone will overflow after 16 days. Use 5th output to extend
the overflow to 256 days.*

## Crafting

Crafting requires 3 [copper ingots](copper_Ingot "wikilink"), 3
[germanium crystals](Germanium_Crystals "wikilink") and 1
[glass.](glass "wikilink") You get 4 Real Time Clock chips.
![Real_Time_Clock.png](Real_Time_Clock.png "Real_Time_Clock.png")

## Understanding Time in the Survivalcraft universe

Remember that this clock displays IN-GAME time and date. In the
description it says the 'tick' is 0.3 seconds and that means *real time*
- NOT game time. The Survivalcraft day is divided into 4096 ticks of
this clock and is about 20 minutes real time. The fourth digit of the
RTC marks the SC days and it changes at midnight.

This means that midnight is at 000, noon is 800 (in Hexadecimal\*),
sunrise is at 400 and sunset at C00 ticks. We can look at the 3rd digit
(from the right) as the 'hour' which gives the SC world a 16 hour day
(instead of 24) and these hours are about one-and-a-quarter real time
minutes. The 2nd digit can be the 'minutes' and they are about 5 seconds
real time. There are 16 minutes to the 'hour'. The 1st digit moves so
fast we usually don't need to include it but it could be the SC 'second'
and of course, there are 16 seconds to the 'minute'.

We can think of the time of day by using just the hour and minute, in a
way similar to 'military time' or the 24 hour clock. The daytime runs
from 4:0 - 5:0 - 6:0 - 7:0 - 8:0 - 9:0 - A:0 - B:0 thru B:F, then at C:0
nighttime begins. The night hours run from C:0 - D:0 - E:0 - F:0 - 0:0 -
1:0 - 2:0 - 3:0 thru 3:F, then at 4:0 daytime begins.

NOTE: Please bear in mind that when we talk about "significant digits"
we count them from right to left, from least significant to the most
significant. That's why the least significant digit output has one pip
on the chip. When we talk about the actual display we typically count
them from left to right, as in a normal digital clock.

  - Hexadecimal is the standard way to show the 16 levels that are used
    in the SC electric 'analog signal' This is a universal convention in
    the digital arena. Since we don't have special characters for the
    numbers beyond 9, the English letters A-F are used. So in Hex, we
    count: 1 2 3 4 5 6 7 8 9 A B C D E F, then 10 11 12 13 14 15 16 17
    18 19 1A 1B 1C 1D 1E 1F 20, etc.

(One could call out the extra digits as: Alf, Burt, Cat, Dan, Ed, Frank.
So sunset would be at "Cat o'clock".)

### Days, Weeks, Months and the Moon

The higher digits, 4 and 5 count out the Survivalcraft days. If we
consider 16 days to the SC 'month' then 16 months to the 'year', that
gives an SC year as 256 days (and the day as 256 minutes).

We know that the [moon](Sun_&_Moon "wikilink") takes 4 days to go
through half of its cycle (from new to full and vice versa) and we may
call this the SC 'week'. This gives us 4 'weeks' to the SC month. It
isn't quite the same as in the real world but is the best compromise,
IMHO. The moon always starts the first day of each month in its new
phase and with a bit more electric work we can even use the RTC to give
us a warning for which nights we can expect to see
[werewolves](Werewolf "wikilink").

## Hooking it up  

The RTC has 5 ouputs on it. Each one is an analog signal which means it
can have 16 values (0-F). Any output can be connected to any electric
that can accept an analog signal but we would normally just use a [digit
display.](7-Segment_Display "wikilink") The least significant digits are
the ones that change the fastest. The least 4 are output on the edges of
the chip and the 5th out the back.

The outputs are identified by the number of pips on each edge. The edge
with one pip is the least significant digit - the fastest one and the
rest follow suit. Once you place the RTC on a surface you can click on
it and it will rotate each click so you can adjust it to the wiring. If
you want to use the 5th output you must place the RTC on a [wire-through
block](Wire_Through_Planks "wikilink").

## Use

### Basic Example

You can make a simple digital wall-type time-of-day clock by using only
the 2nd and 3rd digits. This can be as small as 5 blocks (plus the space
for the digits).

![Ckf.jpg](Ckf.jpg "Ckf.jpg")![Ckb.jpg](Ckb.jpg "Ckb.jpg") This is a
great clock for miners and can be built with the resources found
underground plus [sand](sand "wikilink"). (You do need a crafting table,
too.)

(The time shown means it is nearing midnight.)

To make this clock with a white display, all you need is 6
[Glass](Glass "wikilink") (blocks), 3 [Germanium
Crystals](Germanium_Crystals "wikilink"), 7 [Copper
Ingots](Copper_Ingot "wikilink") and 7
[Cobblestone](Cobblestone "wikilink"). First craft 1 Copper Ingot into
(2) [wires](Electric_Wire "wikilink") and the rest is used for the other
components. Then make (2) displays, (1) wire-through stone block and (1)
RTC. Then put it all together as shown\! There's only seven simple
components and you're done. Yes, the picture is with planks but stone
works just the same.

### **More Examples**

#### **Time plus Date**

This example shows the time as above plus adds the day of the month as
well. It can be useful for knowing when werewolves are about as well as
the time of day. It only requires one more digit and you should make
that digit a different color so it's easy to remember that it shows the
date. ![Date_time_f.jpg](Date_time_f.jpg
"Date_time_f.jpg")![Date_time_r.jpg](Date_time_r.jpg
"Date_time_r.jpg")This shows that it is the 3rd day of this month and is
almost 2 hours past sunrise.

#### **Calendar**

A calendar date display is even simpler than the Basic Time Display.
Just use 2 wire-through-blocks, only 1 wire and align the RTC as shown.
This shows the number of days since the start of the game. The first
digit is the month number and the second is the date of that month. It
starts over at every 'year'. ![Date_f.jpg](Date_f.jpg
"Date_f.jpg")![Date_r.jpg](Date_r.jpg "Date_r.jpg")The number shows
that it is now the 3rd month and the 3rd day of that month. It is NOT
the 33rd day of the year since there are 16 days in each month. It is
(3\*16 + 3) = the 51st day of the year.

#### **Full clock/calendar**

This example uses the full functions of the RTC. It displays all 5
digits to show the full time and calendar date. This is still not very
complicated as you can see by the pictures.

![Full_r.jpg](Full_r.jpg "Full_r.jpg")![Full_f.jpg](Full_f.jpg
"Full_f.jpg")

This display shows that it is the 3rd month, the 4th day of that month
and just past noon (8:0).

#### **Year number display**

It would be very difficult to add a yearly display to any clock above
and is much easier if done as a separate circuit. Only the 5th output is
used since it will overflow on 'new years' day. This circuit must be
built before the first year is over or it will miss counting the first
year. It must always be left undisturbed or it will not be accurate.

***Actually this circuit may not work at all. It was not tested. The
problem is that some electrics will not operate if the character too far
away. The counter may not advance (or even keep its value) if the
character is too far away - even for an instant.***

Start with the RTC and wire the 5th digit to an analog to digital
converter (ADC). This separates each of the 4 bits from the 'analog'
signal. The most significant bit from the ADC will change to '0' on New
Year's Day. This bit is inverted and fed into a 4-bit counter. This
counts the number of years since the circuit was set up. The output of
the counter can be fed to a digit display as shown.

This circuit will count up to 16 years (0 - F). If you really want to
count more than that, the counter can be 'chained'. Look elsewhere for
how to do that.

![Year_f.jpg](Year_f.jpg "Year_f.jpg")![Year_r.jpg](Year_r.jpg
"Year_r.jpg")The way that electrics work, the counter *may*  start at
year 1 unless it's reset *after*  it's built. If so, just remember that
it shows which year you are in rather than the years that have passed.
Or figure out a way to reset it. (The reset is applied to the back of
the counter so is impossible in this design).

## History 

  - The Real Time Clock was added in the 1.23 update.

[Category:Electrics](Category:Electrics "wikilink")
[Category:Crafted](Category:Crafted "wikilink")
---
title: Alarm_circuit
description: 
published: true
date: 2025-10-12T23:30:18.718Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:30:14.431Z
---

## Date / Time Alarm

This circuit is a settable alarm clock. It will read a sign at specific
times on certain dates. These times can be programmed into the memory
devices used. Multiple alarm events are allowed but they will be at the
same times on all days selected. The alarm signal will stay activated
for one hour after the set time.

### Operation

First you must program the dates and times into the [memory
banks](Memory_Bank "wikilink"). The alarm will energize on the dates
selected at the times selected. You cannot have an alarm set for ogne
time at one date and at a different time on another date. It will go off
on ALL selected dates during ALL selected hours. If you need different
date and time settings, you will need separate alarms. Also this design
does not allow an alarm only one hour after another - there must be a
break between alarms. (This can be avoided with additional circuitry).

Edit the sign for the message you want to have displayed at the alarm
time.

When the correct date and time are reached the alarm will automatically
notify you (or the player) with the message on the sign. You can also
tap into the alarm output to activate other circuitry (or a light, door,
etc.) at the alarm time in addition to or instead of the sign.

### Construction

The alarm has no button or display so may not need player interaction
(usually in an Adventure). It may be hidden from view. If you do need to
allow programming, you only need to access the 'front' of the circuit to
get to the memory banks. See the pictures for construction details.

### Programming the memories

Read how to program the [memory banks](memory_Bank "wikilink"). There
are two used in this circuit. One selects the dates and the other sets
the times for the alarm. In this layout, the one next to the RTC
controls the set dates and the one below it sets the times.

Only the first row in each memory has to be programmed. Enter edit mode
and select the first line in the memory chart. Put an 'F' in each column
where you want the alarm to activate. Remember that '0' hours is
midnight, '8' hours is noon and there are 16 hours in each day. Also
remember that date '0' is the first day of each 'month' and there are
only 16 days in each 'month'.

### Pictures

These pictures show the construction of the date/time alarm. It is easy
to build and requires little resources.

<div style="overflow:hidden">

![Hour-Day_alarm_ft.jpg](Hour-Day_alarm_ft.jpg
"Hour-Day_alarm_ft.jpg")![Hour-Day_alarm_rr.jpg](Hour-Day_alarm_rr.jpg
"Hour-Day_alarm_rr.jpg")

</div>

### How it works

This alarm starts with a [RTC](Real_Time_Clock "wikilink") and uses the
3rd (hours) and 4th (days) output from it. These represent the hours and
days of the SC calendar. Each output is fed into a [memory
bank](Memory_Bank "wikilink") which is used as a programmable
comparator. The memories are programmed to output a 'F' at the alarm
time (or date) and '0' all other times. The outputs are then sent to and
'[AND](Logic_AND_Gate "wikilink")' gate which gives the final alarm
signal. That signal is sent to a [sign](Signs "wikilink") (in this
layout) to activate it.

Although the memory bank outputs are technically analog signals, when
used in this fashion, they are effectively digital signals. An analog
signal can be 16 values between 0 and 1 volt. When an analog signal
exceeds 0.7 Volt ('C' or greater) it's sufficient to trigger a digital
gate that follows it.

### Uses

One possible use is to warn the player of nights when werewolves may be
present. The layout in the pictures has a sign written for this purpose.
To have the alarm signal you properly, program the memories as follows:
the date memory must be 000F 000F 000F 000F and the hours memory set to
0000 F000 F000 F000. remember only the first row has to be programmed,
in *this* circuit.

The alarm will warn you at sunrise, noon and sunset on the day BEFORE
the night that werewolves may be active. Wolves can change into
werewolves when the moon is full or new. This happens every 4 days and
is timed with the SC month. On the first day of every month, there is a
new moon and 2 full lunar cycles each month so there are 4 days of
werewolves in each month. With this circuit, you will never be surprised
by werewolves again.

#### Notes

This design keeps the alarm signal on for one full hour once it is
activated. Some applications may not want it to stay on for that long.
You can use a [Pulse Shaper](Clock_/_Pulse_circuits "wikilink") to
shorten this signal.

## Programmable Alarm

This next alarm is simpler to build but is more complicated to program.
It *will* allow you to set alarms for different times on different days.

Instead of programming one line in each of two memories, you have to
program the whole chart in one memory bank.

### Construction

This alarm is simpler to build than the first design and uses fewer
resources. However it is more complicated to program.

<div style="overflow:hidden">

![Palarm_f.jpg](Palarm_f.jpg "Palarm_f.jpg")

</div>

### How it works

The hours and days outputs of the RTC are routed to the address inputs
of the a single memory device. Hours go to the least significant nibble
(4-bits) and the days to the most significant nibble. When programmed
properly, the memory's output will activate the sign at the specific
date/hour combinations.

### Programming the memory

For this alarm, every memory location is accessed so programming the
device is more complicated.

Open the edit window of the memory and familiarize yourself with the
layout of the chart. Across the top are the hex numbers 0 - F. These
indicate the hours of the day. The first column indicates midnight and
the column with '8' indicates noon. Down the left side is another set of
hex digits. These show that the rows in the chart represent the days of
the month.

In order to program an alarm for a specific date/time, scroll down the
chart and tap the line for the date you want to program. The text edit
window will pop up and show the entire row for that particular date. Now
enter an 'F' for each hour you want the alarm to turn on. The first
digit is for midnight, the second for 1:0'clock, etc. Remember you need
to have the alarm turn off before turning it on again. That means you
should NOT set the alarm for two hours in a row since only the first one
will work.

If you want, you can enter the data for ALL hours at the beginning of
the line and let the 'old' digits push off to the right - it won't
matter. In other words, at the beginning of the line, you can type
"F000F000F000F000" and the alarm will go off at midnight, dawn, noon and
sunset. All the extra '0's at the right will be ignored.

You have to program every line for the dates that you want an alarm. If
there is no alarm for a particular date, you can leave that line alone,
assuming it already has all '0's in it.

To program a Werewolf Early Warning System, you type "0000F000F000F000"
in the lines for the dates 3, 7, B and F. All the other lines must be
all '0's. Like above, the alarm will go off at sunrise, noon and sunset
on the days when werewolves may be present that coming night.

The full memory image looks like:

`  || M | 1 | 2 | 3 | 4 | 5 | 6 | 7 || 8 | 9 | A | B | C | D | E | F ||`
`––||––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––||`
`0 ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`1 ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`2 ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`3 || 0 | 0 | 0 | 0 | F | 0 | 0 | 0 || F | 0 | 0 | 0 | F | 0 | 0 | 0 ||`
`4 ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`5 ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`6 ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`7 || 0 | 0 | 0 | 0 | F | 0 | 0 | 0 || F | 0 | 0 | 0 | F | 0 | 0 | 0 ||`
`8 ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`9 ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`A ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`B || 0 | 0 | 0 | 0 | F | 0 | 0 | 0 || F | 0 | 0 | 0 | F | 0 | 0 | 0 ||`
`C ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`D ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`E ||   |   |   |   |   |   |   |   ||   |   |   |   |   |   |   |   ||`
`F || 0 | 0 | 0 | 0 | F | 0 | 0 | 0 || F | 0 | 0 | 0 | F | 0 | 0 | 0 ||`

The rows not filled in are left to all 0's

You can copy the following line from here, open your world in SC, edit
the Memory Bank, select' LINEAR', then paste the line into the bank.
That way you don't have to remember how to program it. 

0000000000000000000000000000000000000000000000000000F000F000F0000000000000000000000000000000000000000000000000000000F000F000F0000000000000000000000000000000000000000000000000000000F000F000F0000000000000000000000000000000000000000000000000000000F000F000F000

This will program your memory bank for the Early Werewolf Warning
Alarm. 

### Daily Alarm

This circuit is also useful as a daily wake-up alarm. The main
difference is that the RTC is connected a little differently.

<div style="overflow:hidden">

![Daily_Alarm_1.jpg](Daily_Alarm_1.jpg "Daily_Alarm_1.jpg")

</div>

It is programmed the same as above but uses hours and minutes, rather
than days and hours

### Wake-up Alarm

To use this to wake the character up, you can have it trigger a
dispenser which shoots a small item at the character. If you use items
with no serious damage, the character will not sustain lasting damage.
Even stone chunks won't hurt much.

You will want to prevent the dispenser from shooting when you aren't
sleeping there. Adding a simple AND gate and switch will work.

<div style="overflow:hidden">

![Daily_Alarm_2.jpg](Daily_Alarm_2.jpg "Daily_Alarm_2.jpg")

</div>

Although that will work, it's easy to forget to turn the alarm off. If
you often sleep elsewhere, you may want to set the alarm each night. You
can replace the toggle switch with a bushbutton latch as shown. Then you
have to enable the alarm every night.

<div style="overflow:hidden">

![Daily_Alarm_3.jpg](Daily_Alarm_3.jpg "Daily_Alarm_3.jpg")

</div>

## 4-Sign Alarm Add-on

This addition adds the capability to have different alarms activate
separately and at different times for different dates. It is the most
versatile alarm but is also the most difficult to program. This circuit
builds on the previous one and you must be comfortable with that design
before attempting this addition. Programming this memory is even much
more complicated than that one.

### Construction

In the pictures, you can see the previous circuit in the background and
the added components for the multiple alarms. Construction is still
fairly simple.

<div style="overflow:hidden">

![4alarm_f.jpg](4alarm_f.jpg
"4alarm_f.jpg")![4alarm_m.jpg](4alarm_m.jpg "4alarm_m.jpg")

</div>

### How it works

The previous design is at the core of this circuit. You can see it at
the back of the first picture. The second picture shows how the addition
is connected to that design.

The output of the memory device is routed to the input of an [Analog to
Digital Converter](Analog_to_Digital_Converter.md "wikilink") (ADC). The
converter decodes the signal and activates one or more of the signs
depending on what value was programmed into the memory.

### Programming the memory

Before attempting to program this design, be sure you are comfortable
with programming the previous one. This design builds on that one and is
more complicated yet\! You also need to fully understand how the ADC
operates. The following explanation assumes you have that knowledge
level.

Instead of programming in an 'F' to activate the alarm, you have to
calculate the value that you need to activate the sign you want. Each of
the 4 bits in the memory's output represents one of the signs. In order
to activate that sign, the bit in that location is set to '1'. If you
program in an 'F', all 4 signs will activate. If you program in a '1',
the first sign will activate. A '2' will activate the second sign, a '4'
the third and an '8' will activate the fourth sign. Programming other
values will activate multiple signs at once.

### Uses

All the applications for the previous alarms can be done with this
design as well. Plus, the ability to have multiple signs and different
time/date combinations make this the most flexible alarm design. This
circuit can replace up to 4 separate Programmable Alarm circuits.

[Category:Circuits](Category:Circuits "wikilink")
[Category:Electricity](Category:Electricity "wikilink")
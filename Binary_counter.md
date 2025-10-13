---
title: Binary_counter
description: 
published: true
date: 2025-10-12T23:33:06.638Z
tags: 
editor: markdown
dateCreated: 2025-10-12T23:33:02.762Z
---

## **Description**

Simple and well-known circuit. Useful for making locks and other things.

Normaly, *1 button press = 1 action* (We will name an action a
modification of the state of the Binary Counter output, which is the
green led in the examples below).

A binary counter adds more possibilities. So with one SR Latch (on the
pictures below there are three) *1 button press = 1 action*, with two SR
Latches *2 button presses*' = *'1 action*, with three SR Latches *4
button presses = 1 action*, and so on.

However, keep in mind that many current-receptive blocks like doors only
react to the rising edge of the signal. Therefore, you need two actions,
which means two modifications of the state of the Binary Counter output,
to make the door move.

The following two slideshows show two 3 SR Latches Binary Counters.

\- When all three leds are lit (ignore the one above the button in the
first slideshow), you have to press four times the button to modify the
green led state, and thus having an action.

\- When all three leds are unlit (ignore the one above the button in the
first slideshow), you have to press four times the button to modify the
green led state, and thus having an action.

Concerning binary numbers, you have to read them form right to left,
again ignoring the led above the button in the first slideshow.

bincalc_0press.jpg Bincalc 7press.jpg Bincalc 6press.jpg Bincalc
5press.jpg bincalc_4press.jpg Bincalc 3press.jpg Bincalc 2press.jpg
bincalc_1press2.jpg Bincalc 8press.jpg

Survivalcraft 2013-07-19 17-36-18-.jpg Survivalcraft 2013-07-19
17-36-22-.jpg Survivalcraft 2013-07-19 17-36-25-.jpg Survivalcraft
2013-07-19 17-36-27-.jpg Survivalcraft 2013-07-19 17-36-29-.jpg
Survivalcraft 2013-07-19 17-36-32-.jpg Survivalcraft 2013-07-19
17-36-34-.jpg Survivalcraft 2013-07-19 17-36-36-.jpg Survivalcraft
2013-07-19 17-36-39-.jpg

## **How to**

Place [SR Latches](SR_Latch "wikilink") on the wall and connect its
ouputs with next one's clock (its on you how much SR Latches you will
use). Then connect SETs and RESETs with [NOT
gates](Logic_NOT_Gate "wikilink"). On the first clock connect button,
and on the last output the thing you want to control (on picture green
LED). You can also put some devices (on picture red LEDs) between [SR
Latches](SR_Latch "wikilink").

![IMG_1445.jpg](IMG_1445.jpg "IMG_1445.jpg")

[Category:Circuits](Category:Circuits "wikilink")
[Category:Electricity](Category:Electricity "wikilink")
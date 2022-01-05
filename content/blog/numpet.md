---
title: "Project Log: Numpet"
date: 2022-01-05T14:37:20-05:00
slug: "numpet"
description: "A simple 4-button Arduino-based keypad for data entry"
keywords: []
draft: true
tags: ["projects", "electronics", "arduino"]
math: false
toc: false
---

## Description

The Numpet is a 4-button "macropad" that uses binary to replicate the featureset of a full number pad. This is accomplished by having each key combination read as a binary number, which then is converted into it's decimal counterpart and sent to the computer as a keyboard input (e. g. Pressing the 1st and 4th button represents 1001 in binary, translating to the number 9). As 4 buttons can represent up to the number 15 in binary, numbers 1-9 output numbers 1-9, number 10 outputs 0 (this is to account for the fact that 0000 is the resting state of the device), and numbers 11-15 represent other functions such as Enter and Backspace.

## Inspiration

The inspiration for this project came from my need for a numpad at work. While shopping for one, I had the random musing that 4 keys would be all that's necessary to be able to enter any number necessary, as well as replicate other functions of a numpad. I then related that to binary, and realized binary was an easy methodology to use for the key combinations.

The name "Numpet" is a portmanteau of "number trumpet", as the 4 buttons reminded me of a trumpet.

## Prototyping

The entirety of my prototyping was done using a $14.99 Pro Micro Starter Kit from microcenter. The kit included, among other things, an Arduino Pro Micro clone, a small breadboard, and hookup wires. This was all I needed to be able to put together this initial prototype.

![](images/numpetproto.jpg "The first prototype")

![](images/numpetproto_bb.png "A rough Fritzing diagram of the prototype")

## Build

For the actual build, I decided to use an Adafruit Perma-Proto breadboard as the base board, with some tactile buttons I had picked up for a previous project, and an Altoids tin as the enclosure. Two standoffs were used to secure the board in place, with 4 more standoffs at the corners to both support the corners of the board on the inside and act as "feet" on the bottom.

### Cost Breakdown

- ~$9.99 - 1x Inland Pro Micro

- ~$4.20 - 1x Adafruit Half-Size Perma-Proto Board

- ~$1.60 - 3x Generic Tactile Buttons

- ~$1.80 - 1x Peppermint Altoids

Total Estimated Cost: $16.59 (plus change for wires and standoffs)

### Assembly

Wiring it all up was very simple. I used the internal pullup resistor, thus all I needed to do was connect one lead of each button to different pins on the Pro Micro, and then connect the other lead to the ground rail on the breadboard, which was then connected to a ground pin on the microcontroller. The breadboard ended up inhibiting by wiring however, as due to the internal connections I had to clip the bottom pins of the buttons (hence the hot glue at the bottom of each button). In addition, it forced me to orient the microcontroller horizontally, when I would have preferred to orient it so that the microUSB port faces out the back.

### Images

![](images/numpetfinal1)
![](images/numpetfinal2)
![](images/numpetfinal3)

### Code

```
INSERT CODE HERE
```

## Final Thoughts

While this ended up being a great first project, and I learned a lot about the basics of working with an Arduino/Arduino-Compatible microcontroller, there were a number of changes I would make if I were able to redo this project:

- I would have gone with a perfboard instead of a breadboard, as the built-in traces ended up limiting my options for board layout.

- I would have used a smaller and cheaper microcontroller as the pro micro was overkill for this project. I planned to use a Trinket for the final project, however I accidentally picked up the Trinket 3v instead of the M0, and the 3v was not suitable for the project.

- I would have went with different buttons. The tactile buttons ended up requiring a lot of force to actuate, and thus are somewhat inefficient for the "typing" style the Numpet requires. I would potentially like to reimplement this later using a Neokey 1x4 with 4 key switches for a better typing experience. Mouse switches may also be an interesting way to implement a lower profile version.

Overall this was an extremely valuable learning experience, and I regard it as a success.
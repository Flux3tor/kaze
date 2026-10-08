---
title: "Kaze."
github: "https://github.com/Flux3tor/Kaze"
description: "A 65% wireless mechanical keyboard."
created_at: "2026-10-07"
total_time: "10h"
---

# October 7, 2026: parts hunt!
<!-- fabricate:entry 184 -->

today i started figuring out what parts i actually wanna use for kaze.

i decided on a **65% wired** design with **USB-C** and **QMK**, and after looking through a bunch of stuff i finally settled on the **HMX Taro switches**, **MDA crystal keycaps**, **durock stabilisers**, **Raspberry Pi Pico**, **SK6812-MINI-E leds**, and **1N4148 diodes**.

i originally wanted kaze to be wireless with an nRF52840 + ZMK and a LiPo, but after realizing how much extra shit that added just for the wireless part, i decided to go wired instead.

this means no battery, no charging circuit, no boost converter, and no power switch. the USB-C connection can just power the board and the LEDs directly, which makes the whole thing way simpler.

i'm also dropping the hotswap sockets. since i've already settled on the Taro switches, i'll just solder them directly into the PCB.

for the case, i've decided to 3d print a **thin case**. it'll use a **screwless tray-mount design**, with the pcb sitting underneath the plate.

i'll have to keep the whole thing under **$125**, but with the wireless stuff gone i've got a little more room to work with. now i can focus on getting the PCB and firmware right.

**next up is finishing the schematic and figuring out the Raspberry Pi Pico pinout!**

_P.S. the keycaps are peak aren't they?_

![](https://fabricate.hackclub-assets.com/864a1ae1934e3fb1d394971c5cadfb7b3b96cc668485bbbc8389e3acbd02f806/image.png)

**Total time spent: 6h**

# October 8, 2026: schematic done!
<!-- fabricate:entry 202 -->

i finally finished the **kaze schematic**.

the whole 5x15 matrix is wired up with the 68 keys and 1N4148 diodes, and the RP2040 is mapped to all the rows and columns.

i also added all **80 SK6812MINI-E LEDs**, with 68 per-key LEDs and 12 underglow LEDs.

i spent a while just moving stuff around and making sure the schematic wasn't turning into a complete mess. getting everything to fit nicely on the sheet actually took longer than i expected lol.

i also went through the connections again before calling it done because i really don't wanna discover some random missing connection after starting the PCB.

the nice thing is that everything is finally in one place now, so i can actually start working on the physical board instead of staring at a bunch of unfinished parts.

so yeah, the **schematic is finally DONE**.

next up: **PCB layout**.

![](https://fabricate.hackclub-assets.com/68e0bbbda73a226a6d7d7dc3b2dfb476c8695472de4f3f202f31ad4a2850537b/image-png/kaze.png)

**Total time spent: 4h**

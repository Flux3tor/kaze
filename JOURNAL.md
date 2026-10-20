---
title: "Kaze."
github: "https://github.com/Flux3tor/Kaze"
description: "A 65% wireless mechanical keyboard."
created_at: "2026-10-07"
total_time: "17h"
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

# October 15, 2026: PCB done!
<!-- fabricate:entry 488 -->

now i finally finished the PCB design for Kaze!! after all the schematic work, component placement, figuring out footprints and routing, the design is finally finalised.

i made a bunch of changes along the way too. i removed the LEDs entirely and switched back to a wired Raspberry Pi Pico setup instead of wireless. basically, i'm keeping things simpler and focusing on getting the keyboard working properly rather than adding features just for the sake of it.

the component placement is done, the PCB design is finalised, and i've started locking in the actual parts i'll be using. i'm looking at the Akko V3 Fairy Pro silent switches, Durock stabilizers, Lakes Mountains PBT keycaps and the other bits needed to bring Kaze to life.

**next up:** designing the case! gotta figure out how the PCB, switches and everything else will fit together and give Kaze a proper look.

![](https://fabricate.hackclub-assets.com/5b3dc5d881adbb0112292c2902fb4b290991c19ca583f4d23cf4772bdebcd0f0/image-png/Screenshot%202026-10-15%20at%2010.32.51%E2%80%AFPM.png)
![](https://fabricate.hackclub-assets.com/96a1b1478c860e009688070f9f8338a7724addc2775445421d040ae804261d31/image-png/kaze-1.png)

**Total time spent: 5h**

# October 19, 2026: case design done!
<!-- fabricate:entry 690 -->

made some solid progress on Kaze today! the case design is finally done, and i also added the silkscreen to the PCB.

for the PCB, i went with a Japanese-inspired aesthetic, adding detailed circuit-style artwork across the board, along with my website, GitHub, and the Kaze branding. also added the 風 character to match the whole theme.

it's finally starting to look like an actual keyboard instead of just a bunch of components on a PCB lol. seeing the board with the silkscreen makes it feel way more personal.

**next up:** firmware! once that's done, i'll submit the whole project for review and hopefully get Kaze one step closer to becoming a real keyboard.

![](https://fabricate.hackclub-assets.com/edf31d55287a3fb696a85de66574d7920347d929d5f514af542ed4925adc8cdc/image-jpeg/0CDDF687-BB7B-4890-8138-25BED83FCE82_1_201_a.jpeg)
![](https://fabricate.hackclub-assets.com/7daa18dc10c628b2ca838354ab6538a946e6e8e860d46245585f132beb88be4e/image-png/image%20%286%29.png)

**Total time spent: 2h**

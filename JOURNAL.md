---
title: "Kaze."
github: "https://github.com/Flux3tor/Kaze"
description: "A 65% wired silent mechanical keyboard."
created_at: "2026-10-07"
total_time: "18h"
---

**# October 7, 2026: parts hunt!**
<!-- fabricate:entry 184 -->

today i started figuring out what parts i actually wanna use for kaze.

i wanted to build a 65% mechanical keyboard with a custom PCB, a 3d printed case and firmware i could customise myself.

at first, i wanted it to be wireless using an nRF52840, ZMK and a LiPo battery. but then i realised how much extra stuff i'd need just for the wireless part. i'd have to deal with charging, the battery and extra power circuitry, so i decided to go wired with USB-C instead. it's simpler, and i'd rather spend my time getting the keyboard itself working.

my parts list changed quite a bit too. i initially looked at HMX Taro switches and MDA Crystal keycaps, and i wanted to add SK6812-MINI-E LEDs for RGB lighting. the original plan had 68 LEDs for the keys and another 12 for underglow.

later, i decided to remove RGB completely. i didn't really need it, and dropping it meant less stuff to deal with on the PCB. i also changed my switch choice to **Akko V3 Fairy Pro silent switches** and picked **Lakes Mountains Premium Cherry PBT keycaps**. i wanted a quieter keyboard, so silent switches made more sense for me.

for the controller, i'm using a USB-C Raspberry Pi Pico development board based on the RP2040. the keys will use a matrix with 1N4148 diodes, and i'll solder the switches directly to the PCB instead of using hot-swap sockets.

for the case, i went with a thin 3d printed design. the idea is to use a screwless tray-mount layout, with the PCB sitting underneath the plate. i'll print it in PLA since i already have filament.

i picked Durock screw-in stabilisers for the larger keys. i had silicone O-rings in the BOM originally, but after getting feedback that they weren't worth the extra cost, i removed them too.

here's the updated BOM with the parts i'm planning to use:

| Name | Purpose | Quantity | Unit Cost (USD) | Total Cost (USD) | Distributor |
|---|---|---:|---:|---:|---|
| [Akko V3 Fairy Pro Switches (Pack of 45)](https://stackskb.com/store/akko-fairy-pro-switch-pack-of-45/) | Mechanical switches | 2 packs | $16.00 | $32.00 | StacksKB |
| [Lakes Mountains Premium Cherry PBT Extended Keycaps](https://curiositycaps.in/products/lakes-mountains-premium-cherry-pbt-extended-keycaps) | Keycaps | 1 | $29.00 | $29.00 | Curiosity Caps |
| [Durock Clear Screw-In Stabilizers V2](https://stackskb.com/store/durock-clear-screw-in-stabilizers-v2/?attribute_combination=4%2B1+Set&attribute_spacebar-size=6.25U) | Stabilizers | 1 | $17.00 | $17.00 | StacksKB |
| [1N4148 Through-Hole Diodes (Pack of 10)](https://stackskb.com/store/1n4148-through-hole-diode/) | Matrix diodes | 7 packs (70 diodes) | ~$0.2857 per pack of 10 | $2.00 | StacksKB |
| [LuatOS USB-C Raspberry Pi Pico Development Board](https://makerbazar.in/products/luatos-usb-c-raspberry-pi-pico-development-board-based-on-rp2040-microcontroller) | Main controller | 1 | $5.00 | $5.00 | MakerBazar |
| [Portronics Type-C to Type-C Cable](https://www.amazon.in/dp/B09Q8XMFHB?ref_=cm_sw_r_cp_ud_dp_9F8YCTNXZB2SQ3WDDXEK_1) | USB connection | 1 | $2.00 | $2.00 | Amazon |
| [PLA Filament](https://india.numakers.com/products/pla-filament) | 3D-printed case | 1 | Already owned | $0.00 | NuMakers |
| PCB | Keyboard circuit board | 5 | $5.00 per PCB | $25.00 | Offline/Local Fabricator |
| **Total** | | | | **$112.00** | |

the budget is around $112 with any extra shipping or taxes. i'm trying not to spend money on features i don't really need, which is why i went with wired instead of wireless and removed the RGB and O-rings.

![](https://cdn.hackclub.com/01a16177-0cd7-7064-a855-fcd0db6ef671/Screenshot_20250408_021218_Google.jpg.png)

**Total time spent: 5h**

**# October 8, 2026: schematic done!**
<!-- fabricate:entry 202 -->

i finally finished the kaze schematic.

i made a 5x15 matrix for the 68 keys and added the 1N4148 diodes. the RP2040 is mapped to the rows and columns, so it can scan the keys without needing a separate pin for every switch.

i also added the RGB LEDs at this point because i was still considering them. that was 80 LEDs in total, with 68 for the keys and 12 for underglow. i ended up removing all of them when i moved on to the PCB, so they're not part of the final design.

most of this stage was getting all the connections down and keeping the schematic readable. i moved things around a bit and checked the wiring because i didn't want to get halfway through the PCB and find out i'd missed something.

once everything was in place, i went through the connections again and called the schematic done. it was nice to finally have the circuit laid out instead of just having a list of parts and ideas.

next up was the PCB layout.

![](https://fabricate.hackclub-assets.com/68e0bbbda73a226a6d7d7dc3b2dfb476c8695472de4f3f202f31ad4a2850537b/image-png/kaze.png)

**Total time spent: 4h**

**# October 15, 2026: PCB done!**
<!-- fabricate:entry 488 -->

now i finally finished the PCB design for kaze!! after the schematic, i started placing components, sorting out footprints and routing the connections.

this was also when i dropped the RGB LEDs completely. the schematic had them, but i didn't want to make the PCB more complicated just for lighting. the final plan is a wired keyboard with the RP2040, the key matrix and the diodes.

i also settled on the parts i'd actually be using: Akko V3 Fairy Pro silent switches, Lakes Mountains PBT keycaps and Durock stabilisers. i wanted the design to match the parts in my BOM instead of the stuff i was considering at the beginning.

getting the placement and routing done took some work, and i had to keep the switch layout and case in mind too. all of these parts need to fit together, so i wanted to get the PCB design sorted before moving further with the case.

the PCB design is done, but i haven't had the board manufactured and tested as a complete keyboard yet. i'll still need to check everything when i can assemble it.

next up: designing the case! gotta figure out how everything will fit together and make kaze look good too.

![](https://fabricate.hackclub-assets.com/5b3dc5d881adbb0112292c2902fb4b290991c19ca583f4d23cf4772bdebcd0f0/image-png/Screenshot%202026-10-15%20at%2010.32.51%E2%80%AFPM.png)
![](https://fabricate.hackclub-assets.com/96a1b1478c860e009688070f9f8338a7724addc2775445421d040ae804261d31/image-png/kaze-1.png)

**Total time spent: 5h**

**# October 19, 2026: case design done!**
<!-- fabricate:entry 690 -->

i finished the case design and worked on the PCB silkscreen too.

for the case, i stuck with a thin 3d printed design. i wanted it to fit the keyboard without making it too bulky, with the PCB sitting underneath the plate. i'll print it in PLA using filament i already have.

i also added the plate to the design and put the keycaps into the render. before that, the render didn't really show what the finished keyboard would look like, so adding them makes it much easier to picture the final build.

i also wanted the PCB to look a bit different instead of leaving it as a plain board. i went with a Japanese-inspired look and added circuit-style artwork, my website, GitHub and the Kaze branding. i added the 風 character as well because it fits the name and the theme.

i think the silkscreen makes the board look much more like my own project. with the plate and keycaps in the render, the whole thing is starting to look more like an actual keyboard.

the case and PCB designs are ready for now, but i'll still need to check the fit properly once i have the physical parts. i haven't assembled the keyboard yet.

next up: firmware! once that's done, i'll have the main designs ready for submission.

![](https://cdn.hackclub.com/01a162fd-a105-7938-9b8f-ceaaf8e3ed8b/Screenshot%202026-10-22%20at%203.03.34%E2%80%AFPM.png)
![](https://fabricate.hackclub-assets.com/7daa18dc10c628b2ca838354ab6538a946e6e8e860d46245585f132beb88be4e/image-png/image%20%286%29.png)

**Total time spent: 2h**

**# October 20, 2026: firmware done!**
<!-- fabricate:entry 766 -->

i originally planned to use QMK, but i ended up going with RMK instead. getting it set up took a bit of debugging.

one issue was the Cargo package name. i'd named the project `Kaze.`, but Cargo wouldn't accept that name, so i had to change it. i also ran into some keymap errors and fixed the configuration before the firmware would build properly.

after sorting those out, i got the firmware to compile for the Raspberry Pi Pico and produce a UF2 file. that was the main thing i wanted to get working, and it was nice to finally have a build that worked after dealing with those errors.

now i've got the schematic, PCB, case design, BOM and firmware ready.

i still haven't tested the complete keyboard physically, so i can't say everything works together yet. i'll need to get the PCB made, put the parts together and test the keys once i can.

for now, the design and firmware are ready, and kaze is ready to be submitted for review.

![](https://fabricate.hackclub-assets.com/e798a1595e27da25e0864d710e492bf8113d3a9d712de30d231a9cda7d0e27e1/image-png/image.png)

**Total time spent: 2h**
---
title: 🛠️ Kinesis Advantage 2
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2024-03-27
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

# Modding Kinesis Advantage 2 (sold)

Used this keyboard since January 20, 2021 and decided it was time to make a custom controller board (🔗[KinT](https://github.com/kinx-project/kint "Github.com | kinx-project / kint")).

> Firmware uses 🔗[QMK](https://config.qmk.fm/#/kinesis/kint36/LAYOUT "QMK Configurator"). I occasionally zap the keybort with my Thor like static discharges. Unplug/replug quick fix.

<br />

<div style="text-align: center;">

![albumimg](/Blog/stuff/images/ka2/0.jpg "Kinesis Advantage 2 LQ with white and light gray DSA keycaps and a Jellycomb touchpad")

> After the mod. The keycaps and cool touchpad wear appeared magically overnight. Must be the KinT swagger.

![albumimg](/Blog/stuff/images/ka2/1.jpg "Small soldering station on a budget friendly manual adjustment standing table")

> Soldered using a 🔗[Pinecil V1](https://wiki.pine64.org/wiki/Pinecil "Pine64 Wiki | Pinecil") powered by a Lenovo power brick (January 10, 2024)

![albumimg](/Blog/stuff/images/ka2/2.jpg "Close up of a Teesny 3.6 with freshly soldered headers and some blistering on the Teensy CPU")

> A bit of splatter. Maybe too much flux (lead-free)

![albumimg](/Blog/stuff/images/ka2/3.jpg "Kitchen counter with budget friendly hot plate soldering equipment")

> GFCI in the kitchen. 300W LED strip soldering hotplate. Probably fine but still.

![albumimg](/Blog/stuff/images/ka2/4.jpg "Close up of freshly soldered SMD components for a KinT keyboard controller")

> Scrapped away accidental bridges while still toasty

![albumimg](/Blog/stuff/images/ka2/5.jpg "Underside of fully soldered KinT keyboard controller")

> PCBs from 🔗[JLCPCB](https://jlcpcb.com/ "JLCPCB") (perfectly fine). First SMD job went well (~15 minutes lead-free)

![albumimg](/Blog/stuff/images/ka2/6.jpg "KinT keyboard controller installed in an open and upside down Kinesis Advantage 2 keyboard")

> Test fit looked good. Empty stress relief opening needed a little more work.

![albumimg](/Blog/stuff/images/ka2/7.jpg "Micro USB to USB-C mount attached to replace the built-in stress relief cable of a Kinesis Advantage 2 keyboard")

> Replaced the built-in stress relief cable with a 🔗[USB-C mount](https://www.aliexpress.us/item/3256807745777636.html "Aliexpress | IP67 Waterproof Cable Micro-USB 2.0 5pin Male to USB-C 3.1") and a 🔗[USB-C to USB-A cable](https://www.aliexpress.us/item/2251832816054825.html "Aliexpress | USB-A to USB-C cable") to complete the build.

> If the above USB-C mount link is dead try this search link: 🔗 [USB-C mount](https://www.aliexpress.us/w/wholesale-Waterproof-Cable-Micro%2525252dUSB-2.0-5pin-Male-to-Usb%2525252dc.html)

<br />

Touchpad gestures: 🔗[libinput-gestures](https://github.com/bulletmark/libinput-gestures "Github | bulletmark / libinput-gestures") 🔗[configured](https://github.com/csmertx/dotfiles/blob/master/config/libinput-gestures.conf "Github | csmertx / dotfiles / config / libinput-gestures.conf") for 3-4 finger gestures (Back/Forward/Home/End/PGUP/PGDN)

<br />

## Teensy Firmware QMK Layouts 1-4 (0-3)

![albumimg](/Blog/stuff/images/ka2/ka2_layout_1.png "Kinesis Advantage QMK Layout Layer 1")

> Main layout

![albumimg](/Blog/stuff/images/ka2/ka2_layout_2.png "Kinesis Advantage QMK Layout Layer 2")

> Caps Lock as function (FN) key to use with custom navigation cluster

![albumimg](/Blog/stuff/images/ka2/ka2_layout_3.png "Kinesis Advantage QMK Layout Layer 3")

> Keypad button switches to a numpad layer I've yet to use successfully

![albumimg](/Blog/stuff/images/ka2/ka2_layout_4.png "Kinesis Advantage QMK Layout Layer 4")

> I remapped the KA2 down key to forward music track instead of this DOS gaming layer (🔗[DBGL](https://dbgl.org/ "DBGL.org") DOSBox frontend and Xbox controller ❤️‍🔥)

> QMK 🔗[json](/Blog/stuff/images/ka2/kinesis_kint36_layout_mertx3000_24_01_12.json "QMK .json file for use with QMK Configurator") for the configurator and 🔗[hex](/Blog/stuff/images/ka2/kinesis_kint36_layout_mertx3000_24_01_12.hex "Hexadecimal file created by the QMK configurator to flash firmware to a Teensy 3.6-4.x") for flashing Teensy firmware. Remapped a few things since, and have no idea where I put my current firmware.

<br />

</div><br />

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 03/27/2024 | Edited: 02/09/2025 | Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Blog/stuff/2024/kinesis_advantage2.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Blog \ stuff \ 2024 \ Kinesis Advantage 2">
       History 🕵️
    </a>
</div>
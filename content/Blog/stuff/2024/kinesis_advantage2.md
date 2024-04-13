---
title: 🛠️ Kinesis Advantage 2
author: csmertx
date: March 27, 2024
weight: -20
---

Modding a Kinesis Advantage 2

> Pieced together 🔗[QMK](https://config.qmk.fm/#/kinesis/kint36/LAYOUT "QMK Configurator") compatible controller via 🔗[KinT](https://github.com/kinx-project/kint "Github.com | kinx-project / kint") kit. Also added custom USB stress relief, and touchpad

> Touchpad gestures: 🔗[libinput-gestures](https://github.com/bulletmark/libinput-gestures "Github | bulletmark / libinput-gestures") 🔗[configured](https://github.com/csmertx/dotfiles/blob/master/config/libinput-gestures.conf "Github | csmertx / dotfiles / config / libinput-gestures.conf") for 3-4 finger gestures (Back/Forward/Home/End/PGUP/PGDN)

<br />

<div style="text-align: center;">

![albumimg](/Blog/stuff/images/ka2/0.jpg "Kinesis Advantage 2 LQ with white and light gray DSA keycaps and a Jellycomb touchpad")

> Coffee bag tie for cable management, and right angle USB for the touchpad.

> Touchpad mess: Sanded the burn marks caused by oil paint pens on card stock paper (whoops)

![albumimg](/Blog/stuff/images/ka2/1.jpg "Small soldering station on a budget friendly manual adjustment standing table")

> Soldered using a 🔗[Pinecil V1](https://wiki.pine64.org/wiki/Pinecil "Pine64 Wiki | Pinecil") powered with a Lenovo laptop power brick

![albumimg](/Blog/stuff/images/ka2/2.jpg "Close up of a Teesny 3.6 with freshly soldered headers and some blistering on the Teensy CPU")

> Splatter from too much flux? (lead-free)

![albumimg](/Blog/stuff/images/ka2/3.jpg "Kitchen counter with budget friendly hot plate soldering equipment")

> GFCI in the kitchen. It's one of those 300W LED strip soldering hotplates, probably fine but still.

![albumimg](/Blog/stuff/images/ka2/4.jpg "Close up of freshly soldered SMD components for a KinT keyboard controller")

> Those little bits are from me scrapping away accidental bridges

> First SMD not as scary as I thought (~15 minutes lead-free)

![albumimg](/Blog/stuff/images/ka2/5.jpg "Underside of fully soldered KinT keyboard controller")

> PCBs from 🔗[JLCPCB](https://jlcpcb.com/ "JLCPCB") (completely functional and lead-free)

![albumimg](/Blog/stuff/images/ka2/6.jpg "KinT keyboard controller installed in an open and upside down Kinesis Advantage 2 keyboard")

> Test fit looked good. Empty stress relief opening needed a little more work.

![albumimg](/Blog/stuff/images/ka2/7.jpg "Micro USB to USB-C mount attached to replace the built-in stress relief cable of a Kinesis Advantage 2 keyboard")

> Replaced the built-in stress relief cable with a 🔗[USB-C mount](https://www.aliexpress.us/item/3256805570910083.html "Aliexpress | IP67 Waterproof Cable Micro-USB 2.0 5pin Male to USB 3.1 Type C Female Panel Mount Water Proof Connector Extension Cord Cable") and a 🔗[USB-C to USB-A cable](https://www.aliexpress.us/item/2251832816054825.html "Aliexpress | USB Type C Cable Fast Charging USb C Cables Type-c Data Cord Charger USB C For Samsung S9 Note 9 Huawei P20 Pro Xiaomi 1m/2m/3m") to complete the build

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

> QMK 🔗[json](/Blog/stuff/images/ka2/kinesis_kint36_layout_mertx3000_24_01_12.json "QMK .json file for use with QMK Configurator") for the configurator and 🔗[hex](/Blog/stuff/images/ka2/kinesis_kint36_layout_mertx3000_24_01_12.hex "Hexadecimal file created by the QMK configurator to flash firmware to a Teensy 3.6-4.x") for flashing Teensy firmware. Remapped a few things since, and have no idea where I put my current firmware. So ah, whoops.

<br />

</div><br />
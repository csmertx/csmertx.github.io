---
title: ⌚ PineTime Smartwatch
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-01
weight: -20
---

<br />

## Pinetime Smartwatch?

~$40 smartwatch with Open Source firmware. And more reliable than any other Android smartwatch in that price range. Mine was shipped and on my wrist within a month (03/23/22 - 04/06/22).

## Reporting in after close to a year

1. Raising wrist to wake up the device is mostly awesome

    > Sometimes waking device displays last notification (swipe to clear notification)

    >  Sometimes waking device displays a random game of pong

2. Vibration is neat to have, but is kind of weak and there's no option to change the vibe pattern

    > Vibe double pulse option for notifications would be helpful

    > Vibe pattern options may be helpful for waking up to alarms

3. Maybe a build without games?

    > Sometimes I find that the watch is playing Pong instead of letting my check the time

4. Touch screen glass held up to a lot of 'abuse'

    > Dismantling a deck, skateboarding, and hitting it on to the corners of door frames and walls.

5. Timer sometimes pauses without a finger tap

6. Holds up fine in the shower, but water drops play havoc on touch screen (expected)

7. Replaced my Casio F91-w

8. Random 'ghost' touches (long arm hairs? finger oil residue? idk)


## Upgrading via Android phone

> Check resources below for Gadetbridge.


## Upgrade firmware to 1.11.x via computer (external watch faces, etc.)

- Download .deb from ITD releases

- Download InfiniTime dfu and resources from InfiniTime 1.11.x release

- ```systemctl --user start itd```


- ```systemctl --user enable itd```

- Connect PineTime watch to PC bluetooth

    - ```itctl fw upg -a ~/Downloads/pinetime-mcuboot-app-dfu-1.11.0.zip -r ~/Downloads/infinitime-resources-1.11.0.zip```


## Shown with Barton 20mm watchband (tricky installation)

<div style="text-align: center;">

<img src="/Linux/Devices/images/pinetime_230122_front.jpg" title="PineTime - Front"/>

<img src="/Linux/Devices/images/pinetime_230122_version.jpg" title="PineTime - Firmware Version"/>

<img src="/Linux/Devices/images/pinetime_230122_back.jpg" title="PineTime - Back with Barton band"/>

<img src="/Linux/Devices/images/pinetime_230122_main.jpg" title="PineTime - Main Menu"/>

<img src="/Linux/Devices/images/pinetime_230122_apps_pg1.jpg" title="PineTime - Apps Page 1"/>

<img src="/Linux/Devices/images/pinetime_230122_apps_pg2.jpg" title="PineTime - Apps Page 2"/>

<img src="/Linux/Devices/images/pinetime_230122_settings_pg1.jpg" title="PineTime - Settings Page 1"/>

<img src="/Linux/Devices/images/pinetime_230122_settings_pg2.jpg" title="PineTime - Settings Page 2"/>

<img src="/Linux/Devices/images/pinetime_230122_settings_pg3.jpg" title="PineTime - Settings Page 3"/>

</div>


## Resources

- [PineTime Store](https://www.pine64.org/pinetime/)

- [PineTime Wiki](https://wiki.pine64.org/index.php/PineTime)

- [InfiniTime Homepage](https://infinitime.io/)

- [InfiniTime Releases](https://github.com/InfiniTimeOrg/InfiniTime/releases)

- [Gadgetbridge Homepage](https://www.gadgetbridge.org/)

- [Gadgetbridge PineTime WiKi](https://codeberg.org/Freeyourgadget/Gadgetbridge/wiki/PineTime)

- [ITD (Starting daemon, etc.)](https://gitea.arsenm.dev/Arsen6331/itd)

- [ITD (Releases)](https://gitea.arsenm.dev/Arsen6331/itd/releases)
---
title: LineageOS
weight: -20
---

## > Samsung Galaxy Tab 3 10in (3G)
- TWRP
    - Installation
        - Download Heimdall
        - Link in resources
    - Access TWRP
        - Volume Up + Power + Home button
        - Release for Samsung splash screen
    - No MTP/OTG Access
```
        $ Connect USB
```
```
        $ adb push /dir/rom.zip /sdcard
```
- ROM Installation
    - Try MTP/OTG or use adb
    - Move ROM.zip to device storage (unzip not necessary)
    - Install (or wipe then install)
    - Wipe the cache afterwards (clears out the ROM)

## > Resources
- Samsung Galaxy Tab 3 10in (3G)
    - https://forum.xda-developers.com/galaxy-tab-3/development-10/rom-lineageos-14-1-t3587761
- TWRP (Tab 3 ...)
    - https://forum.xda-developers.com/galaxy-tab-3/development-10/recovery-twrp-3-x-samsung-galaxy-tab-3-t3340938
- Heimdall
    - https://glassechidna.com.au/heimdall/
    - https://gitlab.com/BenjaminDobell/Heimdall/raw/master/Linux/README

## > Auto rotate issues fix (seems to work)
    $ adb root
    $ adb shell
    $ vim system/build.prop
    ++ log.tag.launcher_force_rotate=VERBOSE
    ++ lockscreen.rot_override=true

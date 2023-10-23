---
title: LineageOS
author: csmertx
date: January 30, 2023
weight: -20
---

<br />

> Open-source Android distribution (OS)

## Samsung Galaxy Tab 3 10in (3G)

- TWRP

    - Installation

        - Download Heimdall (link below)

    - Access TWRP (link below)

        - ```Volume Up``` + ```Power``` + ```Home button```

        - Release for Samsung splash screen

    - No MTP/OTG Access

        ```Connect USB```

        ```adb push /dir/rom.zip /sdcard```

### ROM Installation

1. Try MTP/OTG or use ```adb```

2. Move ROM.zip to device storage (unzip not necessary)

3. Install (or wipe then install)

4. Wipe the cache afterwards (clears out the ROM)

### Auto rotate issues fix

- ```adb root```

- ```adb shell```

- ```vim system/build.prop```

    ```
    ++ log.tag.launcher_force_rotate=VERBOSE
    ++ lockscreen.rot_override=true
    ```

## Resources

- LineageOS ROM for Samsung Galaxy Tab 3 10in (3G)

    - [🔗 xda-developers | Unofficial LineageOS 14.1 for Samsung Galaxy Tab 3 10.1​](https://forum.xda-developers.com/galaxy-tab-3/development-10/rom-lineageos-14-1-t3587761)

- TWRP for Samsung Galaxy Tab 3 10in (3G) 

    - [🔗 xda-developers | [UNOFFICIAL] TWRP 3.x for Samsung Galaxy Tab 3 10.1](https://forum.xda-developers.com/galaxy-tab-3/development-10/recovery-twrp-3-x-samsung-galaxy-tab-3-t3340938)
- Heimdall

    - [🔗 Glass Echidna | Heimdall](https://glassechidna.com.au/heimdall/)

    - [🔗 GitHub | Benjamin-Dobell/Heimdall: tool suite used to flash ROMs onto Samsung Galaxy devices.](https://github.com/Benjamin-Dobell/Heimdall)

- LineageOS

    - [🔗 LineageOS | LineageOS Android Distribution](https://lineageos.org)

    - [🔗 Compatible Device List](https://wiki.lineageos.org/devices/)
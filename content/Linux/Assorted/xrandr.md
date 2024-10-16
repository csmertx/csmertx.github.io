---
title: 💻 XrandR
author: Chris Schammert (csmertx)
published: 2023-01-30
weight: -20
---

<br />

## Mode Not Displayed

1. ```cvt 1600 900```

    > Whatever resolution you need goes here 1920x1080, 3840x2160, etc.

2. Copy line that starts with Modeline

    - ```sudo xrandr --newmode [...copied line minus the word Modeline...]```

        > The --newmode flag or optarg notifies the system of a new Modeline

    - ```sudo xrandr --addmode {vga,Virtual}-{0,1} "1600x900_60.00" #Virtual-1```

        > Included Virtual for Virtual Machines (Slackware can be tricky)

    - ```sudo xrandr --output Virtual-1 --mode "1600x900_60.00"```

        > Whatever output display and mode needed

3. ARandR or System Settings > Display > select new option generated: 1600x900

    > If you don't see the newly generated option reboot and check again

## Resources

- [Arch Wiki: XrandR](https://wiki.archlinux.org/title/Xrandr)

- [ARandR: GUI frontend for XrandR](https://christian.amsuess.com/tools/arandr/)

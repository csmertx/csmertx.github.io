---
title: Monitors
weight: -20
---

## Monitor Resolution config w/xrandr
- cvt 1600 900 60
- vim ~/.xprofile
    - #!/bin/bash
    - xrandr --newmode "1600x900_60.00"  118.25  1600 1696 1856 2112  900 903 908 934 -hsync +vsync
    - xrandr --addmode Virtual-1 1600x900_60.00
    - xrandr --output Virtual-1 1600x900_60.00
- reboot or logout/login

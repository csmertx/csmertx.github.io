---
title: Kubuntu
weight: -20
---

### Disable Automatic Update Check Icon
- Right Click Up Arrow in panel
- Uncheck: General > Extra Items > Updates

### Update Settings
- Muon Package manager > Settings > Software Sources > Updates

### Dist Upgrade
- aptu
- sudo do-release-upgrade -d (?)

### Tiny fonts in GTK applications (2022)
- System Settings > Appearance > Fonts > Enable Force font DPI (96 DPI)

### Incorrect resolution with QEMU
    usermod -a -G video user
    #Switch to virtio
    cvt 1600 900 60
    vim ~/.scripts/kubuntu_virtual_display.sh
        #!/bin/bash
        xrandr --newmode "1600x900_60.00"  118.25  1600 1696 1856 2112  900 903 908 934 -hsync +vsync
        xrandr --addmode Virtual-1 1600x900_60.00
        xrandr --output Virtual-1 1600x900_60.00
    sudo chmod +x ~/.scripts/kubuntu_virtual_display.sh
    #Add new script to Autostart (Windows key > type auto > autostart)
    #Might have to use the GUI to set the display through Settings > Display and Monitor > Resolution drop down menu
    #Reboot
 
 ### Screen tearing (220308)
- sudov /etc/profile.d/kwin.sh
    ```
    #!/bin/sh
    export __GL_YIELD=“USLEEP”
    ```
    - If that doesn't work, clear that line, and add..
    ```
    #!/bin/sh
    export KWIN_TRIPLE_BUFFER=1
    ```
- If the above does nothing then disable KDE compositor and use Picom
    - This is the route that worked for my Quadro K620 & Kubuntu 21.10 (reverted back to KDE/Plasma compositor: 220309)
        - System Settings > Display and Monitor > Compositor > Toggle: Enable compositor on startup
        - apti picom (source w/dependencies included: https://github.com/yshui/picom)
        ```
        cp /usr/share/doc/picom/examples/picom.sample.conf ~/.config/picom.conf
        ```
        - create script:
            ```
            #!/bin/sh
            picom -b
            ```
    - Add Picom script to startup
        - System Settings > Startup and Shutdown > Autostart > Add > Add Login Script
    - Clear tearing for certain applications: 
        - System Settings > Display and Monitor > Compositor > Toggle: Allow applications to block compositing

- Nvidia Developer forum post source: https://forums.developer.nvidia.com/t/screen-tearing/37789/2

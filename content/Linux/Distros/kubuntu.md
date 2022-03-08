### Disable Automatic Update Check Icon
- Right Click Up Arrow in panel
- Uncheck: General > Extra Items > Updates

### Update Settings
- Muon Package manager > Settings > Software Sources > Updates

### Dist Upgrade
- aptu
- sudo do-release-upgrade -d (?)

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
- Or.. Disable KDE compositor and swap with picom
    - This is the route that worked for my Quadro K620 & Kubuntu 21.10
        - System Settings > Display and Monitor > Compositor > Toggle Enable compositor on startup
        - apti picom
        ```
        cp /usr/share/doc/picom/examples/picom.sample.conf ~/.config/picom.conf
        ```
        - create script:
            ```
            #!/bin/sh
            picom -b
            ```
    - Add script to startup: System Settings > Startup and Shutdown > Autostart > Add > Add Login Script

- Nvidia Developer forum post source: https://forums.developer.nvidia.com/t/screen-tearing/37789/2

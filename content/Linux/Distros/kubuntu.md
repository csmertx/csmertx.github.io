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

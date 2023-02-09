---
title: GNOME 3
author: csmertx
date: February 6, 2023
weight: -20
---

# GNOME 3 desktop environment

## Program Not Responsive timeout

> Some older Win32 games may have this issue (e.g. Runes of Magic)

- ```gsettings set org.gnome.mutter check-alive-timeout 120000```

- ```ALT``` + ```F2``` and ```dconf-config```
    - org > gnome > mutter
    - check-alive-timeout: uncheck use default value
    - change from ```5,000``` to ```120,000```

## GDM Enable tap-to-click

- ```sudo -i```

- ```xhost +SI:localuser:gdm```

- ```sudo su gdm -s /bin/bash```

- ```export DISPLAY=:0```

- ```gsettings set org.gnome.desktop.peripherals.touchpad tap-to-click true```

### Reset GDM tap-to-click to default

- ```gsettings reset org.gnome.desktop.peripherals.touchpad tap-to-click```

- ```gsettings reset org.gnome.settings-daemon.peripherals.keyboard numlock-state```

## Open a directory in Nautilus with admin privileges

> Nautilus File Manager

- Open Nautilus

- ```CTRL``` + ```L```

    - ```admin:///dir```

---
title: Gnome 3
weight: -20
---

### Program Not Responsive timeout and Steam/Proton
- gsettings set org.gnome.mutter check-alive-timeout 120000
- dconf-config
    - org > gnome > mutter
    - check-alive-timeout: uncheck use default value
    - change from 5,000 to 120,000

### GDM Enable tap-to-click for those with tap only touchpad devices
- sudo -i
- xhost +SI:localuser:gdm
- sudo su gdm -s /bin/bash
- export DISPLAY=:0
- gsettings set org.gnome.desktop.peripherals.touchpad tap-to-click true
- Restore
    - gsettings reset org.gnome.desktop.peripherals.touchpad tap-to-click
    - gsettings reset org.gnome.settings-daemon.peripherals.keyboard numlock-state

### Open a directory in Nautilus with admin privileges
- Open Nautilus
- CTRL + L
- admin:///dir

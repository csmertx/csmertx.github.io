---
title: 💻 GNOME 3
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-06
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Extensions

- ```apti gnome-extensions-app```

- ```apti chrome-gnome-shell```

- [Auto Move Windows](https://extensions.gnome.org/extension/16/auto-move-windows/)

- [gamemode](https://extensions.gnome.org/extension/1852/gamemode/)

    - ```apti gamemode```

- [Native Window Placement](https://extensions.gnome.org/extension/18/native-window-placement/)

## Autostart (Gnome specific)

- ```ALT``` + ```F2``` and ```gnome-session-properties```

- Gnome tweak-tool (post 3.6?)

    - ```apti gnome-tweaks```

## Autostart (all desktop environments)

- ```mkdir $HOME/.config/autostart```

- ```touch $HOME/.config/autostart/clipit.desktop```

## Center Windows
- ```ALT``` + ```F2``` and ```dconf-editor```

    - org > gnome > mutter > center-new-windows

## Swap Left Win key for Right Win key

> ```Win``` key or ```Super``` key. Whatever you like to call it.

- ```gsettings set org.gnome.desktop.input-sources xkb-options "['grp:lwin_toggle']"```

## Program Not Responsive timeout

> Some older Win32 games may have this issue

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

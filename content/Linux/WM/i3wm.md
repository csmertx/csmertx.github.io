---
title: i3WM
author: csmertx
date: February 6, 2023
weight: -20
---

# i3WM: Tiling window manager

## Mpris Control

- ```apti playerctl```

- ```vim ~/.config/i3/config```
    
    - Bluetooth headsets
    
        - ```bindsym XF86AudioPlay exec --no-startup-id playerctl play-pause```
    
        - ```bindsym XF86AudioPause exec --no-startup-id playerctl play-pause```
    
    - ```xev``` can help determine button press outputs
    
        > See also [keyboard scancodes](/Linux/Devices/keyboard_scancodes) for more bindsym options

- See [mpv](/Linux/Software/mpv) for more about mpris plugin

---
title: 💻 i3WM
author: Chris Schammert (csmertx -- Christopher Schammert)
published: 2023-02-06
weight: -20
---

<br />

## Mpris Control

- ```apti playerctl```

- ```vim ~/.config/i3/config```
    
    - Bluetooth headsets
    
        - ```bindsym XF86AudioPlay exec --no-startup-id playerctl play-pause```
    
        - ```bindsym XF86AudioPause exec --no-startup-id playerctl play-pause```
    
    - ```xev``` can help determine button press outputs
    
        > See also [keyboard scancodes](/Linux/Devices/keyboard_scancodes) for more bindsym options

- See [mpv](/Linux/Software/mpv) for more about mpris plugin

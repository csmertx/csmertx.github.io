---
title: 💻 i3WM
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-06
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

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

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/WM/i3wm.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ WM \ i3WM">
       History 🕵️
    </a>
</div>
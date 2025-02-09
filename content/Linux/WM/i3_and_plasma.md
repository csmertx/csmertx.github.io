---
title: 💻 i3WM & KDE
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-06
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Install Dependencies

```
sudo apt install libxcb1-dev libxcb-keysyms1-dev libpango1.0-dev libxcb-util0-dev libxcb-icccm4-dev libyajl-dev libstartup-notification0-dev libxcb-randr0-dev libev-dev libxcb-cursor-dev libxcb-xinerama0-dev libxcb-xkb-dev libxkbcommon-dev libxkbcommon-x11-dev xutils-dev autoconf
```

## Configuration

- ```vim ~/.config/i3/config```

    ```
    ++ exec --no-startup-id wmctrl -c Plasma
    +++ for_window [title="Desktop — Plasma"] kill, floating enable, border none
    ```

## Avoid tiling popups, dropdown windows from plasma

- ```vim ~/.config/i3/config```

    ```
    ++ for_window [class="plasmashell"] floating enable
    ++ for_window [class="Plasma"] floating enable, border none
    ++ for_window [title="plasma-desktop"] floating enable, border none
    ++ for_window [title="win7"] floating enable, border none
    ++ for_window [class="krunner"] floating enable, border none
    ++ for_window [class="Kmix"] floating enable, border none
    ++ for_window [class="Klipper"] floating enable, border none
    ++ for_window [class="Plasmoidviewer"] floating enable, border none 
    ```

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/WM/i3_and_plasma.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ WM \ i3WM & KDE">
       History 🕵️
    </a>
</div>
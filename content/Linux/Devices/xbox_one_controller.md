---
title: 💻 Xbox One Controller
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-01
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

> Pre-Bluetooth version (wireless)

## Disable Mouse Emulation

- ```vim /usr/share/X11/xorg.conf.d/50-joystick.conf```

    ```
    Driver "joystick"
    ++ Option "StartKeysEnabled" "False"   # These Two Lines Disable
    ++ Option "StartMouseEnabled" "False"  # The mouse emulation
    EndSection
    ```

## LTrigger/RTrigger Issue

- ```apti joystick```

- ```apti jstest-gtk```

- Open ```joystick``` and calibrate (swap Axis 2 with 4 to correct)

## Resources

- [Ask Ubuntu: How can I stop my controller from moving my mouse?](https://askubuntu.com/questions/632026/how-can-i-stop-my-controller-from-moving-my-mouse)

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Devices/xbox_one_controller.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Devices \ Xbox One Controller">
       History 🕵️
    </a>
</div>
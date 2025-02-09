---
title: 📡 Bluetooth
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-01
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Preferred Bluetooth systray

- ```apti blueman```

    > blueman-applet is the desktop status app

    - ```sudo usermod -a -G lp username```

        > Allows user access to DBUS

## USB Tethering 5G

- Ubuntu 22.04: smooth sailing (05-19-22)

- Random disconnects with EndeavourOS (05-19-22)

- Did not try WiFi tethering

## CLI
- ```apti bluez```

    > Arch Linux: ```bluez-tools```

    - ```bluetoothctl```

        - ```bluetoothctl set-alias [Newly discovered device name]```

            - ```bluetoothctl pair [...]```

            - ```bluetoothctl trust [...]```
- Polybar Script

    ```
    wget https://raw.githubusercontent.com/polybar/polybar-scripts/master/polybar-scripts/system-bluetooth-bluetoothctl/system-bluetooth-bluetoothctl.sh
    ```

    - ```vim ~/.config/polybar/config.ini```
    
        ```
        modules-right = system-bluetooth-bluetoothctl battery alsa network sysmenu

        [module/system-bluetooth-bluetoothctl]                                                                                         
        type = custom/script
        exec = ~/.config/polybar/scripts/system-bluetooth-bluetoothctl.sh
        tail = true
        click-left = ~/.config/polybar/scripts/system-bluetooth-bluetoothctl.sh --toggle &
        ```
        
        > Bluetooth Connected unicode symbol = "\uF5AF"

        > Bluetooth Disconnected unicode symbol = "\uF5B1"

## Sources

- [How do you echo a 4-digit Unicode character in Bash?](https://stackoverflow.com/questions/602912/how-do-you-echo-a-4-digit-unicode-character-in-bash)

- [Arch Wiki: Blueman](https://wiki.archlinux.org/title/Blueman)

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Devices/bluetooth.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Devices \ Bluetooth">
       History 🕵️
    </a>
</div>
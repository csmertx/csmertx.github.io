#### Preferred Bluetooth systray
- apti blueman
    - blueman-applet
    - sudo usermod -a -G lp username (access to dbus)
    -
#### USB Tethering (Arch Linux / EndevourOS)
~~~
sudo pacman -Syu usb_modeswitch
~~~
- Seems to be preinstalled via Ubuntu 22.04

#### CLI
- bluez (arch bluez-tools
    - bluetoothctl
        - bluetoothctl set-alias "Newly discovered device name"
            - bluetoothctl pair "..."
            - bluetoothctl trust "..."
- Polybar Script
    - wget https://raw.githubusercontent.com/polybar/polybar-scripts/master/polybar-scripts/system-bluetooth-bluetoothctl/system-bluetooth-bluetoothctl.sh
- vim ~/.config/polybar/config.ini
    ```
    ...
    modules-right = system-bluetooth-bluetoothctl battery alsa network sysmenu
    ...

    [module/system-bluetooth-bluetoothctl]                                                                                         
    type = custom/script
    exec = ~/.config/polybar/scripts/system-bluetooth-bluetoothctl.sh
    tail = true
    click-left = ~/.config/polybar/scripts/system-bluetooth-bluetoothctl.sh --toggle &
    ```
- Bluetooth Connected unicode symbol = "\uF5AF"
- Bluetooth Disconnected unicode symbol = "\uF5B1"

#### Sources
- https://stackoverflow.com/questions/602912/how-do-you-echo-a-4-digit-unicode-character-in-bash
- https://wiki.archlinux.org/title/Blueman

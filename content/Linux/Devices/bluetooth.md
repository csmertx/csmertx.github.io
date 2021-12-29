### Preferred Bluetooth systray
- apti blueman
    - blueman-applet

### CLI
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
- Bluetooth Connected symbol = "\uF5AF"
- Bluetooth Disconnected symbol = "\uF5B1"

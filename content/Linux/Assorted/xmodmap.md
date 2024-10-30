---
title: 💻 Xmodmap
author: Chris Schammert (csmertx -- Christopher Schammert)
published: 2023-01-30
weight: -20
---

<br />

> Only for Xorg desktops (No Wayland support atm)

## Using Xmodmap to remap Caps Lock as a FN key

Remapping Caps Lock as a modifier key for navigation (hjkl ui nm)

> Mapped keys: h = ```Left```, j = ```Down```, k = ```Up```, l = ```Right```, u = ```PGDN```, i = ```PGUP```, n = ```Home```, m = ```End```

- ```vim /home/user/.Xmodmap```

    ```
    keycode 66 = Mode_switch  
    keysym h = h H Left  
    keysym l = l L Right  
    keysym k = k K Up
    keysym j = j J Down
    keysym n = n N End
    keysym m = m M Home
    keysym i = i I KP_Prior
    keysym u = u U KP_Next
    keysym o = o O KP_Insert
    keysym p = p P KP_Delete
    keysym q = q Q Escape
    keysym 1 = 1 exclam                 F1
    keysym 2 = 2 at                     F2
    keysym 3 = 3 numbersign             F3
    keysym 4 = 4 dollar                 F4
    keysym 5 = 5 percent                F5
    keysym 6 = 6 asciicircum            F6
    keysym 7 = 7 ampersand              F7
    keysym 8 = 8 asterisk               F8
    keysym 9 = 9 parenleft              F9
    keysym 0 = 0 parenright             F10
    #keysym minus = minus underscore     F11
    #keysym equal = equal plus           F12 
    ```

    > See [Keyboard Scancodes](/Linux/Devices/keyboard_scancodes) for key additional  options

- Test with ```xmodmap ~/.Xmodmap```

## Loading Xmodmap after login

- ```vim /home/user/.config/autostart/xmodmap.desktop```

    ```
    [Desktop Entry]
    Type=Application
    Exec=xmodmap arrow keys
    Hidden=false
    NoDisplay=false
    X-GNOME-Autostart-enabled=true
    Name[en_US]=xmodmap
    Name=xmodmap
    Comment[en_US]=xmodmap /home/user/.Xmodmap
    Comment=xmodmap /home/user/.Xmodmap
    ```

    > Unless your user name is ```user``` this needs to be changed: ```/home/user/.Xmodmap```

- ```sudoc /home/user/.config/autostart/xmodmap.desktop```

- Or include ```xmodmap ~/.Xmodmap``` in your startup script

## Resources

- [Arch Wiki: Xmodmap](https://wiki.archlinux.org/title/Xmodmap)
### Laptop
- vim /etc/X11/xorg.conf.d/10-libinput.conf
```
Section "InputClass"
    Identifier "touchpad catchall"
    Driver "synaptics"
    MatchIsTouchpad "on"
    MatchDevicePath "/dev/input/event*"
        Option "TapButton1" "1"
        Option "TapButton2" "3"
        Option "TapButton3" "2"
        Option "HorizTwoFingerScroll" "on" # set to off if edge
        Option "VertTwoFingerScroll" "on" # set to off if edge
        Option "HorizEdgeScroll" "on"
        Option "VertEdgeScroll" "on"
EndSection
```

### Gestures (USB touchpad/touchpads with multi-touch)
- Requires: wmctrl && xdotool (Debian/Ubuntu: libinput-tools)
- sudo gpasswd -a $USER input
- git clone https://github.com/bulletmark/libinput-gestures
    - cd libinput-gestures
    - sudo make install
    - cp /etc/libinput-gestures.conf ~/.config/libinput-gestures.conf
    - libinput-gestures-setup autostart
    - libinput-gestures-setup start
- After edits to libinput-gestures.conf run libinput-gestures-setup stop/start

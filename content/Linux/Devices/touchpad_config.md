---
title: 💻 Touchpads
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-06-30
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Jelly Comb glass slow cursor w/Ubuntu 22.04

> Rendered my touchpad unusable for a few weeks

- ```libinput list-devices```

    - HTX USB HID Device HTX HID Device Mouse

- [Upgraded to Ubuntu](/Linux/Distros/ubuntu) (Kubuntu) 23.04

    - Tracking as expected after upgrading to 22.10, then 23.04

## Laptop

- ```vim /etc/X11/xorg.conf.d/10-libinput.conf```

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

## Gestures

> For touchpad/touchpads with multi-touch capabilities

- Requires: ```wmctrl``` and ```xdotool``` 

    > Debian/Ubuntu: ```libinput-tools``` + ```wmctrl``` + ```xdotool``` 

- ```sudo gpasswd -a $USER input```

- ```git clone https://github.com/bulletmark/libinput-gestures```

    - ```cd libinput-gestures```

    - ```sudo make install```

    - ```cp /etc/libinput-gestures.conf ~/.config/libinput-gestures.conf```

    - ```libinput-gestures-setup autostart```

    - ```libinput-gestures-setup start```

- After edits to ```libinput-gestures.conf``` run ```libinput-gestures-setup [stop/start]```

    - Example config edits
    
        > Confirmed with Jelly Comb USB Touchpad)

        ```
        ###############################################################################
        # SWIPE GESTURES:
        ###############################################################################

        # Note the default is an "internal" command that uses wmctrl to switch
        # workspaces and, unlike xdotool, works on both Xorg and Wayland (via
        # XWayland). It also can be configured for vertical and horizontal
        # switching over tabular workspaces, as per the example below. You can
        # also add "-w" to the internal command to allow wrapping workspaces.
        # Ensure you install wmctrl if you use _internal.

        # Move to next workspace (works for GNOME/KDE/etc on Wayland and Xorg)
        #gesture swipe up	_internal ws_up 
        gesture swipe up 4 xdotool key Home                         # <---- Home key
        gesture swipe down 4 xdotool key End                        # <---- End key


        # NOTE ABOUT FINGER COUNT:
        # The above command will configure this command for all fingers (i.e. 3
        # for 4) but to configure it for 3 fingers only, change it to:
        # gesture swipe up	3 _internal ws_up
        # Then you can configure something else for 4 fingers or leave 4 fingers
        # unconfigured. You can configure an explicit finger count like this for
        # all example commands in this configuration file.
        #
        # gesture swipe up	xdotool key super+Page_Down

        # Move to prev workspace (works for GNOME/KDE/etc on Wayland and Xorg)
        #gesture swipe down	_internal ws_down
        # gesture swipe down	xdotool key super+Page_Up

        # Browser go forward (works only for Xorg, and Xwayland clients)
        gesture swipe right 3 xdotool key Alt_L+Right               # <---- Forward (browser)
        gesture swipe up 3 xdotool key Page_Up                      # <---- PGUP key
        gesture swipe down 3 xdotool key Page_Down                  # <---- PGDN key

        # Browser go back (works only for Xorg, and Xwayland clients)
        gesture swipe left 3 xdotool key Alt_L+Left                 # <---- Back (browser)
        ```

        > Swipe 4 fingers up is ```Home```, down is ```End```, 3 is ```PGUP```, ```PGDN```

        > Swipe 3 fingers left is ```Back```, right is ```Foward```

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Devices/touchpad_config.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Devices \ Touchpads">
       History 🕵️
    </a>
</div>
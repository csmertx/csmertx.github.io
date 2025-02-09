---
title: 🖲️ Trackballs
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2024-04-22
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Elecom HUGE trackball FN Buttons

<br /><div style="text-align: center;">

![Photo](/Linux/Devices/images/elecom_huge_wired_catbus_for_scale_800x800.jpg)

> Apoxie Sculpt palm rest and 'Catbus So Many Poses!' 'blind box' figurine for scale

</div><br />

Elecom HUGE button remapping via GUI: 🔗[input-remapper](https://github.com/sezanzeb/input-remapper)

> Requires escalated privileges

Restore presets for each reboot/poweroff

- ```sudo systemctl enable input-remapper```

- ```sudo systemctl start input-remapper```

- Apply presets & make sure ```Autoload``` is toggled

#### Copy/Paste with Tmux, Refresh, and Undo (how I have mine configured)

- FN1 -> Shift + Ctrl + v

- FN2 -> F5

- FN3 -> Ctrl + z

## Logitech Trackman Marble via X11 + 🔗[libinput](https://man.archlinux.org/man/xorg.conf.5#INPUTCLASS_SECTION "Archlinux | Manuals / xorg.conf / Inputclass Section")

```
Trackball Scrolling
/etc/X11/xorg.conf.d/10-libinput.conf

Section "InputClass"
        Identifier      "Marble Mouse"
        MatchProduct    "Logitech USB Trackball"
        Driver          "libinput"
        Option          "ScrollMethod" "button"
        Option          "ScrollButton" "8"
        #Option          "ScrollButton" "9" #left handed scrolling
    Option      "MiddleEmulation" "on"
EndSection


/etc/X11/xorg.conf.d/10-evdev.conf

#       - - - Logitech Marble Mouse Settings - - -
#
#       The Logitech Marble Mouse buttons are mapped [A-D] from left to right:
#       A (large); B (small) |  C (small); D (large).
#
#       Preferred options for right-handed usage:#       - - - Logitech Marble Mouse Settings - - -
#
#       The Logitech Marble Mouse buttons are mapped [A-D] from left to right:
#       A (large); B (small) |  C (small); D (large).
#
#       Preferred options for right-handed usage:
#       A = normal click [1]
#       B = middle-click [2]
#       C = middle-click [2]
#       D = right-click [3]
#       Hold button B while rolling trackball to emulate wheel-scrolling.
#
#       Preferred options for left-handed usage:
#       A = right-click [3]
#       B = middle-click [2]
#       C = middle-click [2]
#       D = normal click [1]
#       Hold button C while rolling trackball to emulate wheel-scrolling.
#       Pressing both large buttons simultaneously (b) produces a "back" action.

Section "InputClass"
        Identifier  "Marble Mouse"
        MatchProduct "Logitech USB Trackball"
        MatchIsPointer "on"
        MatchDevicePath "/dev/input/event*"
        Driver "evdev"

#       Physical button #s:     A b D - - - - B C
#       Option "ButtonMapping" "1 8 3 4 5 6 7 2 2"   right-hand placement
#       Option "ButtonMapping" "3 8 1 4 5 6 7 2 2"   left-hand placement
#       b = A & D
        Option "ButtonMapping" "1 8 3 4 5 6 7 2 2"

#       EmulateWheel: Use Marble Mouse trackball as mouse wheel
#       Factory Default: 8; Use 9 for right side small button
        Option "EmulateWheel" "true"
        Option "EmulateWheelButton" "8"#       - - - Logitech Marble Mouse Settings - - -
#
#       The Logitech Marble Mouse buttons are mapped [A-D] from left to right:
#       A (large); B (small) |  C (small); D (large).
#
#       Preferred options for right-handed usage:
#       A = normal click [1]
#       B = middle-click [2]
#       C = middle-click [2]
#       D = right-click [3]
#       Hold button B while rolling trackball to emulate wheel-scrolling.
#
#       Preferred options for left-handed usage:
#       A = right-click [3]
#       B = middle-click [2]
#       C = middle-click [2]
#       D = normal click [1]
#       Hold button C while rolling trackball to emulate wheel-scrolling.
#       Pressing both large buttons simultaneously (b) produces a "back" action.

Section "InputClass"
        Identifier  "Marble Mouse"
        MatchProduct "Logitech USB Trackball"
        MatchIsPointer "on"
        MatchDevicePath "/dev/input/event*"
        Driver "evdev"

#       Physical button #s:     A b D - - - - B C
#       Option "ButtonMapping" "1 8 3 4 5 6 7 2 2"   right-hand placement
#       Option "ButtonMapping" "3 8 1 4 5 6 7 2 2"   left-hand placement
#       b = A & D
        Option "ButtonMapping" "1 8 3 4 5 6 7 2 2"

#       EmulateWheel: Use Marble Mouse trackball as mouse wheel
#       Factory Default: 8; Use 9 for right side small button
        Option "EmulateWheel" "true"
        Option "EmulateWheelButton" "8"
#       - - - Logitech Marble Mouse Settings - - -
#
#       The Logitech Marble Mouse buttons are mapped [A-D] from left to right:
#       A (large); B (small) |  C (small); D (large).
#
#       Preferred options for right-handed usage:
#       A = normal click [1]
#       B = middle-click [2]
#       C = middle-click [2]
#       D = right-click [3]
#       Hold button B while rolling trackball to emulate wheel-scrolling.
#
#       Preferred options for left-handed usage:
#       A = right-click [3]
#       B = middle-click [2]
#       C = middle-click [2]
#       D = normal click [1]
#       Hold button C while rolling trackball to emulate wheel-scrolling.
#       Pressing both large buttons simultaneously (b) produces a "back" action.

Section "InputClass"
        Identifier  "Marble Mouse"
        MatchProduct "Logitech USB Trackball"
        MatchIsPointer "on"
        MatchDevicePath "/dev/input/event*"
        Driver "evdev"

#       Physical button #s:     A b D - - - - B C
#       Option "ButtonMapping" "1 8 3 4 5 6 7 2 2"   right-hand placement
#       Option "ButtonMapping" "3 8 1 4 5 6 7 2 2"   left-hand placement
#       b = A & D
        Option "ButtonMapping" "1 8 3 4 5 6 7 2 2"
#       - - - Logitech Marble Mouse Settings - - -
#
#       The Logitech Marble Mouse buttons are mapped [A-D] from left to right:
#       A (large); B (small) |  C (small); D (large).
#
#       Preferred options for right-handed usage:
#       A = normal click [1]
#       B = middle-click [2]
#       C = middle-click [2]
#       D = right-click [3]
#       Hold button B while rolling trackball to emulate wheel-scrolling.
#
#       Preferred options for left-handed usage:
#       A = right-click [3]
#       B = middle-click [2]
#       C = middle-click [2]
#       D = normal click [1]
#       Hold button C while rolling trackball to emulate wheel-scrolling.
#       Pressing both large buttons simultaneously (b) produces a "back" action.

Section "InputClass"
        Identifier  "Marble Mouse"
        MatchProduct "Logitech USB Trackball"
        MatchIsPointer "on"
        MatchDevicePath "/dev/input/event*"
        Driver "evdev"

#       Physical button #s:     A b D - - - - B C
#       Option "ButtonMapping" "1 8 3 4 5 6 7 2 2"   right-hand placement
#       Option "ButtonMapping" "3 8 1 4 5 6 7 2 2"   left-hand placement
#       b = A & D
        Option "ButtonMapping" "1 8 3 4 5 6 7 2 2"

#       EmulateWheel: Use Marble Mouse trackball as mouse wheel
#       Factory Default: 8; Use 9 for right side small button
        Option "EmulateWheel" "true"
        Option "EmulateWheelButton" "8"

#       EmulateWheelInertia: How far (in pixels) the pointer must move to
#       generate button press/release events in wheel emulation mode.
#       Factory Default: 50
        Option "EmulateWheelInertia" "10"

#       Axis Mapping: Enable vertical [ZAxis] and horizontal [XAxis] scrolling
        Option "ZAxisMapping" "4 5"
#       Option "XAxisMapping" "6 7"

#       Emulate3Buttons: Required to interpret simultaneous press of two large
#       buttons, A & D, as a seperate command, b.
#       Factory Default: true
        Option "Emulate3Buttons" "true"
EndSection
#       EmulateWheel: Use Marble Mouse trackball as mouse wheel
#       Factory Default: 8; Use 9 for right side small button
        Option "EmulateWheel" "true"
        Option "EmulateWheelButton" "8"

#       EmulateWheelInertia: How far (in pixels) the pointer must move to
#       generate button press/release events in wheel emulation mode.
#       Factory Default: 50
        Option "EmulateWheelInertia" "10"

#       Axis Mapping: Enable vertical [ZAxis] and horizontal [XAxis] scrolling
        Option "ZAxisMapping" "4 5"
#       Option "XAxisMapping" "6 7"

#       Emulate3Buttons: Required to interpret simultaneous press of two large
#       buttons, A & D, as a seperate command, b.
#       Factory Default: true
        Option "Emulate3Buttons" "true"
EndSection
#       EmulateWheelInertia: How far (in pixels) the pointer must move to
#       generate button press/release events in wheel emulation mode.
#       Factory Default: 50
        Option "EmulateWheelInertia" "10"

#       Axis Mapping: Enable vertical [ZAxis] and horizontal [XAxis] scrolling
        Option "ZAxisMapping" "4 5"
#       Option "XAxisMapping" "6 7"

#       Emulate3Buttons: Required to interpret simultaneous press of two large
#       buttons, A & D, as a seperate command, b.
#       Factory Default: true
        Option "Emulate3Buttons" "true"
EndSection

#       EmulateWheelInertia: How far (in pixels) the pointer must move to
#       generate button press/release events in wheel emulation mode.
#       Factory Default: 50
        Option "EmulateWheelInertia" "10"

#       Axis Mapping: Enable vertical [ZAxis] and horizontal [XAxis] scrolling
        Option "ZAxisMapping" "4 5"
#       Option "XAxisMapping" "6 7"

#       Emulate3Buttons: Required to interpret simultaneous press of two large
#       buttons, A & D, as a seperate command, b.
#       Factory Default: true
        Option "Emulate3Buttons" "true"
EndSection
#       A = normal click [1]
#       B = middle-click [2]
#       C = middle-click [2]
#       D = right-click [3]
#       Hold button B while rolling trackball to emulate wheel-scrolling.
#
#       Preferred options for left-handed usage:
#       A = right-click [3]
#       B = middle-click [2]
#       C = middle-click [2]
#       D = normal click [1]
#       Hold button C while rolling trackball to emulate wheel-scrolling.
#       Pressing both large buttons simultaneously (b) produces a "back" action.

Section "InputClass"
        Identifier  "Marble Mouse"
        MatchProduct "Logitech USB Trackball"
        MatchIsPointer "on"
        MatchDevicePath "/dev/input/event*"
        Driver "evdev"

#       Physical button #s:     A b D - - - - B C
#       Option "ButtonMapping" "1 8 3 4 5 6 7 2 2"   right-hand placement
#       Option "ButtonMapping" "3 8 1 4 5 6 7 2 2"   left-hand placement
#       b = A & D
        Option "ButtonMapping" "1 8 3 4 5 6 7 2 2"

#       EmulateWheel: Use Marble Mouse trackball as mouse wheel
#       Factory Default: 8; Use 9 for right side small button
        Option "EmulateWheel" "true"
        Option "EmulateWheelButton" "8"

#       EmulateWheelInertia: How far (in pixels) the pointer must move to
#       generate button press/release events in wheel emulation mode.
#       Factory Default: 50
        Option "EmulateWheelInertia" "10"

#       Axis Mapping: Enable vertical [ZAxis] and horizontal [XAxis] scrolling
        Option "ZAxisMapping" "4 5"
#       Option "XAxisMapping" "6 7"

#       Emulate3Buttons: Required to interpret simultaneous press of two large
#       buttons, A & D, as a seperate command, b.
#       Factory Default: true
        Option "Emulate3Buttons" "true"
EndSection
```

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Devices/trackball_scrolling.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Devices \ Trackballs">
       History 🕵️
    </a>
</div>
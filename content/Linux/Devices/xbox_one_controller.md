---
title: Xbox One Controller
weight: -20
---

### Disable Mouse Emulation
**Sourced:** askubuntu.com/questions/632026/how-can-i-stop-my-controller-from-moving-my-mouse

=> vim /usr/share/X11/xorg.conf.d/50-joystick.conf

```
	...
	Driver "joystick"
	++ Option "StartKeysEnabled" "False"   # These Two Lines Disable
	++ Option "StartMouseEnabled" "False"  # The mouse emulation
EndSection
```

### LTrigger/RTrigger Issue
- apti joystick
- apti jstest-gtk
- Open joystick and calibrate (swap Axis 2 with 4 to correct)

---
title: Openbox+
author: csmertx
date: February 6, 2023
weight: -20
---

# Openbox Extra Stuff

> ```rc.xml``` edit to add keyboard shortcuts for media keys, i3, and more

- ```vim /home/user/.config/openbox/rc.xml```

> Don't forget to swap ```user``` with your own ```$USER``` name

```
    <!-- Keybinding for rofi -->
    <keybind key="W-d">
      <action name="Execute">
        <command>rofi -show run</command>
      </action>
    </keybind>
    <!-- Keybinding for zen run -->
    <keybind key="W-r">
      <action name="Execute">
        <command>/home/user/.scripts/zen_run</command>
      </action>
    </keybind>
    <!-- Keybinding for terminal -->
    <keybind key="W-t">
      <action name="Execute">
        <command>terminology</command>
      </action>
    </keybind>
    <!-- Keybinding for i3lock -->
    <keybind key="W-9">
      <action name="Execute">
        <command>betterlockscreen -l</command>
      </action>
    </keybind>
    <!-- Keybindings for Media Keys -->
    <keybind key="XF86AudioMute">
      <action name="Execute">
        <command>amixer -q -D pulse sset Master toggle</command>
      </action>
    </keybind>
    <keybind key="XF86AudioLowerVolume">
      <action name="Execute">
        <command>/home/user/.scripts/vol_notify_minus</command>
      </action>
    </keybind>
    <keybind key="XF86AudioRaiseVolume">
      <action name="Execute">
        <command>/home/user/.scripts/vol_notify_plus</command>
      </action>
    </keybind>
    <keybind key="XF86AudioPlay">
      <action name="Execute">
        <command>/home/user/.scripts/music_play</command>
      </action>
    </keybind>
    <keybind key="XF86AudioPrev">
      <action name="Execute">
        <command>/home/user/.scripts/music_next</command>
      </action>
    </keybind>
    <keybind key="XF86AudioNext">
      <action name="Execute">
        <command>/home/user/.scripts/music_next</command>
      </action>
    </keybind>
    <keybind key="XF86AudioStop">
      <action name="Execute">
        <command>killall ncmpcpp</command>
      </action>
    </keybind>
<!-- Window Tiling: Emulates Windows 7 Snap feature -->
<keybind key="W-Left">
  <action name="UnmaximizeFull"/>
  <action name="MaximizeVert"/>
  <action name="MoveResizeTo">
    <width>50%</width>
  </action>
  <action name="MoveToEdgeWest"/>
</keybind>
<keybind key="W-Right">
  <action name="UnmaximizeFull"/>
  <action name="MaximizeVert"/>
  <action name="MoveResizeTo">
    <width>50%</width>
  </action>
  <action name="MoveToEdgeEast"/>
</keybind> 
```

## Zen Run?

- ```apti zenity```

> Hacky Bash script version of GNOME's ```gnome-do``` program (```ALT``` + ```F2```)

- ```vim ~/.scripts/zen_run```

  ```
  #!/usr/bin/bash

  #### Minimal run menu similar to: gmrun, lxpanel run, and gnome-do
  # prompt for shell command and execute whenever
  RUN=$(zenity --width=400 --entry --title "Run Command" --text="Run" 2> /dev/null)
  $SHELL -c "$RUN"
  ```

- ```chmod +x ~/.scripts/zen_run```
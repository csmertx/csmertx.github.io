=> vim /home/chris/.config/openbox/rc.xml
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
        <command>/home/chris/.scripts/zen_run</command>
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
        <command>/home/chris/.scripts/vol_notify_minus</command>
      </action>
    </keybind>
    <keybind key="XF86AudioRaiseVolume">
      <action name="Execute">
        <command>/home/chris/.scripts/vol_notify_plus</command>
      </action>
    </keybind>
    <keybind key="XF86AudioPlay">
      <action name="Execute">
        <command>/home/chris/.scripts/music_play</command>
      </action>
    </keybind>
    <keybind key="XF86AudioPrev">
      <action name="Execute">
        <command>/home/chris/.scripts/music_next</command>
      </action>
    </keybind>
    <keybind key="XF86AudioNext">
      <action name="Execute">
        <command>/home/chris/.scripts/music_next</command>
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

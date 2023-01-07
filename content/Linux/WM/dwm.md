---
title: DWM > Dynamic Window Manager
weight: -20
---

## Dynamic Window Manager Notes

### Compile

### config.def.h
- Fonts
    - ```static const char *fonts[]     = "hack:size=10";```
    - ```static const char dmenufont[]    = "hack:size=10";```
- default terminal
    - ```static const char *termcmd[]       = { "terminal-name", NULL };```
- Fix window gaps
    - ```-- static cont int resizehints = 1;```
    - ```++ static cont int resizehints = 0;```

### No ~/.xinitrc
- cp /etc/X11/xinit/xinitrc-common ~/.xinitrc (best)
- cp /etc/X11/xinit/xinitrc ~/.xinitrc (meh)

### bar
- Add to ~/.xinitrc
```while true
while true; do
    xsetroot -name " CentOS 8.1 | $USER@$HOSTNAME | $(hostname -I| awk '{print $1}') | $(date "+%F %R") "```
    sleep 1m
done &

### background
- Add to ~/.xinitrc
- feh --bg-scale ~/Pictures/backgrounds/789948.jpg
- feh --bg-scale ~/Pictures/backgrounds/789948.jpg (twice cuz reasons)

### startx
- Add to ~/.xinitrc
- exec dwm

### Display
- Save layout from arandr
- cat that layout to whatever dwm autostart script

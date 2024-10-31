---
title: 💻 Dynamic Window Manager (DWM)
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-01-31
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Compile

### config.def.h

- Fonts

    - ```static const char *fonts[]     = "hack:size=10";```

    - ```static const char dmenufont[]    = "hack:size=10";```

- default terminal

    - ```static const char *termcmd[]       = { "terminal-name", NULL };```

- Fix window gaps

    - ```-- static cont int resizehints = 1;```

    - ```++ static cont int resizehints = 0;```

## No ~/.xinitrc

- ```cp /etc/X11/xinit/xinitrc-common ~/.xinitrc```

    > Recommended

- ```cp /etc/X11/xinit/xinitrc ~/.xinitrc```

    > Not recommended

## Status bar

- Add to ```~/.xinitrc```

    ```
    while true
    while true; do
        xsetroot -name " CentOS 8.1 | $USER@$HOSTNAME | $(hostname -I| awk '{print $1}') | $(date "+%F %R") "
        sleep 1m
    done &
    ```

    > Status line output = CentOS 8.1 | chris@c1n1 | [IP ADDRESS] | 2023-02-05 18:28 (See [below](#resources) for date scripting)

## Wallpaper
- Add to ```~/.xinitrc```

- ```feh --bg-scale ~/Pictures/backgrounds/789948.jpg```

- ```feh --bg-scale ~/Pictures/backgrounds/789948.jpg```

    > Twice because that was the only way it would work for sone reason

## startx

- Add to ```~/.xinitrc```

- ```exec dwm```

## Display

- Save layout from ```arandr```

- cat that layout to whatever dwm autostart script

## Resources

- [nixCraft: How To Format Date For Display or Use In a Shell Script](https://www.cyberciti.biz/faq/linux-unix-formatting-dates-for-display/)
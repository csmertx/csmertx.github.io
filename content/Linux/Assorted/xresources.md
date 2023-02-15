---
title: X resources
author: csmertx
date: January 30, 2023
weight: -20
---

<br />

> Set padding, DPI, anti-alising, Xcursor theme, X font settings, etc.

> Time saver for certain terminal emulators (URxvt, xterm, etc.)

## Xresources Example

- ```vim ~/.Xresources```

    ```
    ! Xresources
        
    Xft.dpi: 96
    Xft.hinting: true
    Xft.rgba: rgb
    Xft.autohint: true
    Xft.hintstyle: auto

    XTerm*termName: xterm-256color

    XTerm.vt100.faceName: Hack:size=13:antialias=true

    XTerm.vt100.locale: true
    XTerm.vt100.geometry: 100x35

    ! special
    *.foreground:   #464646
    *.background:   #f7f7f7
    *.cursorColor:  #464646

    ! black
    *.color0:       #101010
    *.color8:       #525252

    ! red
    *.color1:       #7c7c7c
    *.color9:       #7c7c7c

    ! green
    *.color2:       #8e8e8e
    *.color10:      #8e8e8e

    ! yellow
    *.color3:       #a0a0a0
    *.color11:      #a0a0a0
    ! blue
    *.color4:       #686868
    *.color12:      #686868

    ! magenta
    *.color5:       #747474
    *.color13:      #747474

    ! cyan
    *.color6:       #868686
    *.color14:      #868686

    ! white
    *.color7:       #b9b9b9
    *.color15:      #2e2e2e
    ```

    > Example fixes some common font and color rendering issues (Arch, Slackware, etc.)

## Resources

- [Arch Wiki: X resources](https://wiki.archlinux.org/title/X_resources)

- [ASCII-Code: HTML Color Names](https://www.ascii-code.com/html-color-names)

- [terminal.sexy: Design, edit and share terminal colorschemes](https://terminal.sexy/)
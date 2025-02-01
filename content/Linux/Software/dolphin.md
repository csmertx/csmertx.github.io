---
title: 💻 Dolphin (KDE)
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-03
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

###### <p style="font-size:12px"><span style="color:dimgray">_Created: 12/29/2021 | Edited: 01/31/2025 | Author: Chris Schammert (csmertx) | [History 🕵️](https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Software/dolphin.md "Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Software \ Dolphin (KDE)")_</span></p>

<br />

## Right-click menu to extract archives (zip, etc.)

```apti ark dolphin-plugins```

## Select file/folder with single click (for shift click or alt click selections)

- System Settings (appz) > Workspace Behaviour > General Behavior > Clicking files or folders > Selects them


## SSH with Fish

- In the url/path bar

    - ```fish://user@ipaddress```

    - Stream media from another PC..

## Custom Right Click Menu

- ```kf5-config --path services```

- ```vim $HOME/.local/share/kservices5/ServiceMenus/action.desktop```

    > Copy path Example (See [below for menu entry options](#resources))

    > Copy Path is now builtin as of 02/03/23

    ```
    [Desktop Entry]
    Type=Service
    Icon=edit-copy
    X-KDE-ServiceTypes=KonqPopupMenu/Plugin
    MimeType=directories;all/all;
    Actions=cppath;
    Encoding=UTF-8
    Terminal=false
    
    [Desktop Action cppath]
    Name=Copy Path
    Icon=edit-copy
    Exec=echo "%f" | xclip -selection c
    Terminal=false
    ```

- Can't Copy Folder Path

    - Settings > Configure Dolphin > Services > Check Copy Path

    - Right click folder > Actions > Copy Path

## Resources

- [Freedesktop.org: Recognized desktop entry keys](https://specifications.freedesktop.org/desktop-entry-spec/latest/ar01s06.html)

- [Images Service menu for Dolphin (KDE)](https://github.com/caco3/kim5)

    > Right click to rotate images, convert from to png/jpg/gif, and more
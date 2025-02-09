---
title: 💻 Zathura
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-04
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

> Keyboard driven document viewer

## Configuring

### Default config

- ```cp /usr/share/doc/zathura/examples/zathurarc ~/.config/zathura/zathurarc```

### Copy to clipboard

- ```vim ~/.config/zathura/zathurarc```

    ```
    ++ set selection-clipboard clipboard
    ```

### Dual page

> side-by-side mode: press ```d```

- ```vim ~/.config/zathura/zathurarc```

    ```
    ++ set first-page column 1:1
    ```

### Titlebar

- ```vim ~/.config/zathura/zathurarc```

    ```
    ++ window-title-basename
    ++ window-title-home-tilde
    ++ statusbar-basename
    ++ statusbar-home-tilde
    ```

### Invert Colors

- ```vim ~/.config/zathura/zathurarc```

    ```
    ++ set default-fg "#DCDCCC"
    ++ set default-bg "#2C2C2C"
    ++ set inputbar-fg "#DCDCCC"
    ++ set inputbar-bg "#2C2C2C"
    ++ set statusbar-fg "#DCDCCC"
    ++ set statusbar-bg "#2C2C2C"
    ++ set recolor-lightcolor "#2C2C2C" #reversed on purpose
    ++ set recolor-darkcolor "#DCDCCC" #likewise
    ++ set recolor
    ```

## Bookmarks

- ```bmark pg10```

    - Saves bookmark ```pg10```

- ```blist``` + ```TAB```

    - lists bookmarks

## Resources

- [pwmt.org: Zathura](https://pwmt.org/projects/zathura/)

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Software/zathura.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Software \ Zathura">
       History 🕵️
    </a>
</div>
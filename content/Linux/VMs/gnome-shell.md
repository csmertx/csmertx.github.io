---
title: Gnome Shell
author: csmertx
date: February 5, 2023
weight: -20
---

### Extensions

- ```apti gnome-extensions-app```

- ```apti chrome-gnome-shell```

- [Auto Move Windows](https://extensions.gnome.org/extension/16/auto-move-windows/)

- [gamemode](https://extensions.gnome.org/extension/1852/gamemode/)

    - ```apti gamemode```

- [Native Window Placement](https://extensions.gnome.org/extension/18/native-window-placement/)

### Autostart (Gnome specific)

- ```ALT``` + ```F2``` and ```gnome-session-properties```

- Gnome tweak-tool (post 3.6?)

    - ```apti gnome-tweaks```

### Autostart (all desktop environments)

- ```mkdir $HOME/.config/autostart```

- ```touch $HOME/.config/autostart/clipit.desktop```

### Center Windows
- ```ALT``` + ```F2``` and ```dconf-editor```

    - org > gnome > mutter > center-new-windows

## Swap Left Win key for Right Win key

> ```Win``` key or ```Super``` key. Whatever you like to call it.

- ```gsettings set org.gnome.desktop.input-sources xkb-options "['grp:lwin_toggle']"```

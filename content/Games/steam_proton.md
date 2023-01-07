---
title: Steam Proton (Linux)
weight: -20
---

#### WINED3D instead of Vulcan (If no Vulcan support)
- Library > Right click game > Properties
    - SET LAUNCH OPTIONS
        - PROTON_USE_WINED3D=1 %command%

#### Vulcan On (should be default in 2022?)
- Library > Right click game > Properties
    - SET LAUNCH OPTIONS
        - +r_renderapi 1

#### Debug Log per game
- SET LAUNCH OPTIONS
    - DEBUGGER=gdb steam
- Library > Right click game > Properties
    - SET LAUNCH OPTIONS
        - -con_logfile

#### Protontricks
- https://flathub.org/apps/details/com.github.Matoking.protontricks
```
bashrc
++ alias protontricks='flatpak run com.github.Matoking.protontricks'
bashsrc
```
```
protontricks -s "Name Of Super Awesome Game"
```
```
protontricks GAMEIDNUMBER --gui
```

---
title: 🕹️ Proton (Linux)
author: Chris Schammert (csmertx -- Christopher Schammert)
published: 2023-01-30
weight: -20
---

<br />

## Right click menu not working

- ```Settings``` > ```Interface``` > ```Enable content focus compatibility mode```

## WINED3D instead of Vulcan (If no Vulcan support)

- Library > Right click game > Properties

    - SET LAUNCH OPTIONS

        - ```PROTON_USE_WINED3D=1 %command%```

## Vulcan On (set by default 2022?)

- Library > Right click game > Properties

    - SET LAUNCH OPTIONS

        - ```+r_renderapi 1```

## Debug Log per game

- SET LAUNCH OPTIONS

    - ```DEBUGGER=gdb steam```

- Library > Right click game > Properties

    - SET LAUNCH OPTIONS

        - ```-con_logfile```

## Protontricks

- [🔗 Install Protontricks](https://flathub.org/apps/details/com.github.Matoking.protontricks): A simple wrapper that does winetricks things for Proton enabled games

    - ```flatpak install flathub com.github.Matoking.protontricks```

    - ```flatpak run com.github.Matoking.protontricks```

- Use Protontricks

    - ```bashrc```

    - ```++ alias protontricks='flatpak run com.github.Matoking.protontricks'```

    - ```bashsrc```

    - ```protontricks -s "Name Of Super Awesome Game"```

    - ```protontricks GAMEIDNUMBER --gui```


<br />
<br />

## Resources

- 🔗[Github | GloriousEggroll / proton-ge-custom / releases](https://github.com/GloriousEggroll/proton-ge-custom/releases)

---
title: 💻 AwesomeWM
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-05
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

> See also [AwesomeWM | Floppier DE](/Linux/WM/awesome_floppier) for more theming

## Easy Mode Theming

- ```mkdir ~/.config/awesome```

- ```cd ~/.config/awesome```

- ```git clone --recursive https://github.com/lcpz/awesome-copycats.git```

- ```cp ~/.config/awesome/awesome-copycats/rc.lua.template ~/.config/awesome/rc.lua```

## Edit city_id for weather status

- ```vim ~/.config/awesome/awesome-copycats/themes/vertex/theme.lua```

    > line ~277

    - Visit: https://openweathermap.org

        - ```Search City```

        - https://openweathermap.org/city/4156404 = ```city_id = 4156404,```

        > Gainesville, FL ```city_id = 4156404```

## Startup Applications

- ```su```

- ```mkdir /etc/awesomebackup```

- ```cp /etc/xdg/awesome/rc.lua /etc/awesomebackup```

    > Or: ```mkdir ~/.config/awesome && cp /etc/xdg/awesome/rc.lua ~/.config/awesome```

- ```sudov /etc/xdg/awesome/rc.lua```

    > Or: ```vim ~/.config/awesome/rc.lua```

    ```
        ++ -- Autorun programs
        ++ autorun = true
        ++ autorunApps =
        ++ {
        ++    "redshift",
        ++ }
        ++ if autorun then
        ++    for app = 1,
        ++        awful.util.spawn(autorunApps[app])
        ++    end
        ++ end
    ```

## Touchpad

- See also [Touchpad](/Linux/Devices/touchpad_config)

## Resources

- [GitHub - lcpz/awesome-copycats: Awesome WM themes](https://github.com/lcpz/awesome-copycats)

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/WM/awesome.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ WM \ AwesomeWM">
       History 🕵️
    </a>
</div>
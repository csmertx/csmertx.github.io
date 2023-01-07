---
title: AwesomeWM
weight: -20
---

### Easy Mode Theming
- mkdir ~/.config/awesome
- cd ~/.config/awesome
- git clone --recursive https://github.com/lcpz/awesome-copycats.git
- cp ~/.config/awesome/awesome-copycats/rc.lua.template ~/.config/awesome/rc.lua

### Edit city_id for weather status
- vim ~/.config/awesome/awesome-copycats/themes/vertex/theme.lua (line ~277)
    - city_id = 4156404, -- Gainesville, Florida
- Gainesville, FL city_id = 4156404

### Startup Applications
- su
- mkdir /etc/awesomebackup
- cp /etc/xdg/awesome/rc.lua /etc/awesomebackup
- or: mkdir ~/.config/awesome && cp /etc/xdg/awesome/rc.lua ~/.config/awesome
- sudov /etc/xdg/awesome/rc.lua (or vim ~/.config/awesome/rc.lua)
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
### Touchpad
- See ../Notes/Linux/Devices/touchpad_config.md

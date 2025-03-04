---
title: 💻 Plasma (KDE)
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2024-07-02
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

###### <p style="font-size:12px"><span style="color:dimgray">_Created: 02/10/2023 | Edited: 02/02/2025 | Author: Chris Schammert (csmertx) | [History 🕵️](https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/DEs/kde_plasma.md "Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Desktop Environments \ Plasma (KDE)")_</span></p>

## Exclude firmware updates

- Discover (KDE Software Center) > Settings > Uncheck: ```vendor-directory - Vendor (Automatic)```

- Lenovo X270 BIOS (firmware) 1.50+ update incompatible with aftermarket batteries. Also mentioned 🔗 [here](/Windows_and_DOS/win_dos_vm#windows-activation-in-vm "Windows and DOS VMs / Windows Activation in VM")

    - Link above includes BIOS rollback procedure (_confirmed as of January 9th, 2024_). Batteries will charge again.

## SDDM High CPU Usage (25% +)

- ```sudov /etc/security/pam_env.conf```

    ```
    ...
    ++ QT_QUICK_BACKEND DEFAULT=software
    ```

## Disable File Indexer baloo_file

- ```balooctl disable```

- pause with: ```balooctl suspend```

## Breeze SDDM theme background

> When GUI selection does not represent selection

- ```sudo mkdir /usr/share/backgrounds/new_folder```

- ```cp /folder/image.jpg /usr/share/backgrounds/new_folder/image.jpg```

- ```sudov /usr/share/sddm/themes/breeze/theme.conf.user```

    ```
    ++ background=/usr/share/backgrounds/new_folder/image.jpg
    ```

- Logout & login

## Time set to 24 hours instead of 12 hours in SDDM

> Solution to change SDDM time display to 12 hours

- ```sudov /etc/locale.conf```

    ```
    ++ LANG=en_US.UTF-8
    ```

- sudov /etc/locale.gen

    ```
    -- #en_US.UTF-8 UTF-8
    ++ en_US.UTF-8 UTF-8
    ```

- ```locale-gen```

## Removal (Arch)

- ```pac -Rc plasma```

- ```pac -Rc kwallet```

## Auto kdewallet login

> May minimize security

- Make sure wallet is named: ```kdewallet```

- Access Control > Prompt when an application accesses a wallet

- Change password to blank & blank

- Log-out/Log-in and always allow trusted applications

    > wifi, etc.)

## User icons/avatars location

- ```/usr/share/kpackage/kcms/kcm_users/contents/img```

## Virtual Keyboard in SDDM
- ```sudov /etc/sddm.conf.d/sddm.conf```

    ```
    ++ [General]
    ++ InputMethod=qtvirtualkeyboard
    ```

## KDE Wallet Auto Login

- ```pac -S kwallet-pam```

- Disable: "Close when last application stops using it" in KDE Wallet settings

- Does not seem to work with fingerprint reader login

    > Confirmed does not with Thinkpad X1

- If all else fails and one just needs WiFi at login: Change KDE Wallet password to a blank password

## Enable tap-to-click external touchpad

- ```sudov /usr/share/X11/xorg.conf.d/40-libinput.conf```

    - In > ```Identifier``` ```libinput touchpad catchall``` add line > ```option "Tapping" "True"```
        
        > After > ```MatchIsTouchpad "on"```

## Dedicated GPU with oversized fonts and scaling (Xorg)

- Regardless of DPI scaling set in Plasma

- ```vim ~/.Xdefaults```

    ```
    ++ Xft.dpi: 96
    ```

- Log out and login

## Disable Bluetooth auto power-on at startup

- ```Super Key``` + search term: ```autostart```

    - Background Services > Uncheck bluetooth

    - Can be re-enabled through the System tray via Plasma panel

## Unsupported resolution with monitors not connecting (Kubuntu 22.04)

- ```CTRL``` + ```ALT``` + ```F3```

- Backup folder ```/home/user/.local/share/kscreen``` as kscreen_ (or something like that)

- Delete ```/home/user/.local/share/kscreen```

- ```reboot```

## Linux Mint | KDE Plasma Clipboard Emoji Support

- ```apts emoji``` or ```sudo aptitude search emoji```

    - If needed ```apti fonts-noto-color-emoji```

- ```sudov /etc/fonts/local.conf```

```
<?xml version="1.0"?>
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
<fontconfig>
 <alias>
   <family>sans-serif</family>
   <prefer>
     <family>Noto Sans</family>
     <family>Noto Color Emoji</family>
     <family>Noto Emoji</family>
     <family>DejaVu Sans</family>
   </prefer> 
 </alias>

 <alias>
   <family>serif</family>
   <prefer>
     <family>Noto Serif</family>
     <family>Noto Color Emoji</family>
     <family>Noto Emoji</family>
     <family>DejaVu Serif</family>
   </prefer>
 </alias>

 <alias>
  <family>monospace</family>
  <prefer>
    <family>Noto Mono</family>
    <family>Noto Color Emoji</family>
    <family>Noto Emoji</family>
    <family>DejaVu Sans Mono</family>
   </prefer>
 </alias>
</fontconfig>
```
- ```fc-cache```
- Logout + login

    - SSH Note: It helps to have synced host/guest terminal emulator configuration for visual parity.

## Resources

- 🔗 [r/kde | Constant CPU usage when sddm-greeter is idle (references: sddm/sddm Issue #323)](https://www.reddit.com/r/kde/comments/u4chnl/constant_cpu_usage_when_sddmgreeter_is_idle/)

- 🔗 [GitHub | sddm/sddm - high cpu when sddm-greeter is idle · Issue #323](https://github.com/sddm/sddm/issues/323)

- 🔗 [DEV Community | Get emojis working on arch linux with noto-fonts-emoji](https://dev.to/darksmile92/get-emojis-working-on-arch-linux-with-noto-fonts-emoji-2a9 "DEV Community | Get emojis working on arch linux with noto-fonts-emoji")

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 02/10/2023 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/DEs/kde_plasma.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ DEs \ Plasma (KDE)">
       History 🕵️
    </a>
</div>
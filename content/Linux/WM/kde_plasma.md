#### Disable File Indexer baloo_file
- balooctl disable
- pause with: balooctl suspend

#### Breeze SDDM theme background woes
- sudo mkdir /usr/share/backgrounds/new_folder
- cp /folder/image.jpg /usr/share/backgrounds/new_folder/image.jpg
- sudov /usr/share/sddm/themes/breeze/theme.conf.user
- ++ background=/usr/share/backgrounds/new_folder/image.jpg
- Logout and see what's what

#### Time set to 24 hours instead of 12 hours in SDDM
=> sudov /etc/locale.conf (prob forgot to do this one..)
=> ++ LANG=en_US.UTF-8
=> sudov /etc/locale.gen
=> -- #en_US.UTF-8 UTF-8
=> ++ en_US.UTF-8 UTF-8
=> locale-gen

#### Removal (Arch)
- pac -Rc plasma
- pac -Rc kwallet

#### Automagical kdewallet login (might minimize some security)
- Make sure wallet is named: kdewallet
- Access Control > Prompt when an application accesses a wallet
- Change password to blank & blank
- Log-out/Log-in and always allow trusted applications (wifi, etc.)

#### User icons/avatars location
- /usr/share/kpackage/kcms/kcm_users/contents/img

#### Virtual Keyboard in SDDM
- sudov /etc/sddm.conf.d/sddm.conf
    - [General]
    - InputMethod=qtvirtualkeyboard

#### KDE Wallet Auto Login
- pac -S kwallet-pam
- Disable: "Close when last application stops using it" in KDE Wallet settings
- Does not work with fingerprint reader login
- If all else fails and one just needs WiFi at login: Change KDE Wallet password to a blank password

#### Enable tap-to-click external touchpad
- sudov /usr/share/X11/xorg.conf.d/40-libinput.conf
    - In > Identifier "libinput touchpad catchall" add line > option "Tapping" "True"
    - After > MatchIsTouchpad "on"

#### Dedicated GPU with oversized fonts and scaling (Xorg)
- Regardless of DPI scaling set in Plasma
- vim ~/.Xdefaults
    - Add: Xft.dpi: 96
- Log out and login

#### Disable Bluetooth auto power-on at startup
- Super Key + search term: autostart
    - Background Services > Uncheck bluetooth
    - Can be re-enabled through the System tray via Plasma panel

#### Unsupported resolution with monitors not connecting (Kubuntu 22.04)
- CTRL + ALT + F3
- Backup folder /home/user/.local/share/kscreen as kscreen_ (or something like that)
- Delete /home/user/.local/share/kscreen
- Reboot

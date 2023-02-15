---
title: Flatpaks
author: csmertx
date: February 3, 2023
weight: -20
---

<br />

## Flathub

- ```flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo```

- ```reboot```
    
    > Or logout/login

## Desktop Files

- ```vim $HOME/{.bashrc,.zshrc}```
    
    ```
    ++ export XDG_DATA_DIRS="~/.local/share/flatpak/exports/share/applications;/var/lib/flatpak/exports/share/applications"
    ```

## Uninstall a flatpak

- ```flatpak list```

- ```flatpak remove [org.flatpak.package]```

## org.freedesktop.Platform.openh264 fails...

- ```flatpak install flathub org.freedesktop.Platform```

## Visual Studio Code

- Install: ```flatpak install flathub com.visualstudio.code```

- Run: ```flatpak run com.visualstudio.code```

### Glade

- Install: ```flatpak install flathub org.gnome.Glade```

- Run: ```flatpak run org.gnome.Glade```

### Atom Editor

- Install: ```flatpak install flathub io.atom.Atom```

- Run: ```flatpak run io.atom.Atom```

## Glimpse (fork of Gimp)

- Install: ```flatpak install flathub org.glimpse_editor.Glimpse```

- Run: ```flatpak run org.glimpse_editor.Glimpse```

## Firefox Beta (beta/beta)

- ```flatpak install --user https://flathub.org/beta-repo/appstream/org.mozilla.firefox.flatpakref```

## ONLYOFFICE

- Install: ```flatpak install flathub org.onlyoffice.desktopeditors```

- Run: ```flatpak run org.onlyoffice.desktopeditors```

## Calibre

- Install: ```flatpak install flathub com.calibre_ebook.calibre```

- Run: ```flatpak run com.calibre_ebook.calibre```

### Ubuntu (19.10)

- ```sudo add-apt-repository ppa:alexlarsson/flatpak```

- ```sudo apt update```

- ```sudo apt install flatpak```

- ```sudo apt install gnome-software-plugin-flatpak```

- ```sudo apt install plasma-discover-backend-flatpak```

- ```flatpak remove-add --if-not-exists flathop https://flathub.org/repo/flathub.flatpakrepo```

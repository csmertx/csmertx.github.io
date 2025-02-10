---
title: 🏄 Firefox
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-07
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Firefox Stop Auto Updating

- ```sudov /etc/firefox/policies/policies.json```

  > Kubuntu 21.10
  ```
  {
    "policies": {
        "AppAutoUpdate": false
    }
  }

  ```

## Firefox manual installation

- Download: [Firefox for Linux](https://www.mozilla.org/en-US/firefox/linux/)

- And move contents to ```/opt/firefox```


### Desktop environment start menu and taskbar launcher

- ```/home/usr/.local/share/applications/firefox.desktop```

  ```
  [Desktop Entry]
  Categories=WebBrowser
  Comment[en_US]=Firefox Web Browser
  Comment=Firefox Web Browser
  Exec=/opt/firefox/firefox-bin
  GenericName[en_US]=Web Browser
  GenericName=Web Browser
  Icon=/home/usr/Pictures/Icons/Firefox.png
  MimeType=
  Name[en_US]=Firefox
  Name=Firefox
  Path=
  StartupNotify=false
  Terminal=false
  TerminalOptions=
  Type=Application
  X-DBUS-ServiceName=
  X-DBUS-StartupType=
  X-KDE-SubstituteUID=false
  X-KDE-Username=
  ```

  > Don't forget to change ```user``` to ```$USER``` and grab a copy of the [Firefox icon](https://i.imgur.com/lBvUY2K.png)

- ```sudo chmod +x /home/user/.local/share/applications/firefox.desktop```

- Sometimes a logout is required to show new start menu options

## Resources

- [GitHub - mozilla/policy-templates: Policy Templates for Firefox](https://github.com/mozilla/policy-templates)

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 03/08/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Web/firefox.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Web \ Firefox">
       History 🕵️
    </a>
</div>
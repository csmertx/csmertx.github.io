---
title: 🏄 Firefox
author: Chris Schammert (csmertx)
published: 2023-02-07
weight: -20
---

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

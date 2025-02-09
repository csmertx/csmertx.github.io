---
title: 💻 Java Apps
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-01-31
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Installation (Linux)

> Satisfy dependencies (e.g. Kingdom of Loathing: KoLMafia)

- ```sudo apti default-jdk```

## Create desktop shortcuts for Java apps

> For all those delightful .jar files

- ```vim ~/.local/share/applications/kolmafia.desktop```

    ```
    [Desktop Entry]
    Comment[en_US]=Kingdom of Loathing Mafia Client
    Comment=Kingdom of Loathing Mafia Client
    Exec=java -jar /home/chris/.sources/KoLmafia-20755.jar
    GenericName[en_US]=KoLmafia
    GenericName=KoLmafia
    Icon=/home/chris/Pictures/Icons/swordandmartini_dark_theme.png
    Name[en_US]=KoLmafia
    Name=KoLmafia
    StartupNotify=true
    Terminal=false
    Type=Application
    Categories=Game
    ```

- ```sudoc /home/chris/.local/share/applications/kolmafia.desktop```

- Launch in KDE Plasma: Start Menu > Games > KoLmafia

    > Logout and login for some desktop environments

## Resources

- [Swordandmartini.png: For dark desktop themes](/Linux/Code/images/swordandmartini_dark_theme.png)

- [Swordandmartini.png: For light desktop themes](/Linux/Code/images/swordandmartini_light_theme.png)

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Code/java.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Code \ Java Apps">
       History 🕵️
    </a>
</div>
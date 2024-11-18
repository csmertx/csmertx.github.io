---
title: 🕹️ Skyrim Special Edition
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-03-27
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Screen tearing (for slow camera movement)

- Ubuntu

    - ```vim "/home/user/.steam/debian-installation/steamapps/common/Skyrim Special Edition/Skyrim/SkyrimPrefs.ini"```

- Custom Steam games location

    - ```vim ".../SteamLibrary/steamapps/common/Skyrim Special Edition/Skyrim/SkyrimPrefs.ini"```

- Add ```iPresentInterval=0``` as the last entry in ```[Display]```

    ```
    [Display]
    ...
    ++ iPresentInterval=0
    ```

## Mouse Acceleration (for slow mouse movement)

- Ubuntu

    - ```vim /home/user/.steam/debian-installation/steamapps/common/Skyrim Special Edition/Skyrim/SkyrimPrefs.ini```

- Custom Steam games location

    - ```vim .../SteamLibrary/steamapps/common/Skyrim Special Edition/Skyrim/SkyrimPrefs.ini```

- Add ```bMouseAcceleration=0``` as the last entry in ```[Controls]```

    ```
    [Controls]
    ...
    ++ bMouseAcceleration=0
    ```

## Nvidia P620 + Linux Mint 21.3

- Lost access to The Elder Scrolls IV (Oblivion) and V (Skyrim) on September 20th, 2023

    - Possibly due to this 🔗 [bug](https://www.protondb.com/app/22330#sL_KcHMBYi "ProtonDB.com | Game Details for The Elder Scrolls IV: Oblivion GOTYE \ After getting the game to actually launch, it plays perfectly with very few issues. Mod managers however mostly have no Linux support.").

        - My P620 is a business class card like their NVIDIA RTX A4500
    
    - No issues with XFX Radeon RX 6400 as of a few weeks ago

## Resources

- [🔗 Bethesda Support: What do I do if my mouse has a delay while playing The Elder Scrolls V: Skyrim?](https://help.bethesda.net/#en/answer/27025)
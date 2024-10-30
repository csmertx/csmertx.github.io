---
title: 🕹️ Skyrim Special Edition
author: Chris Schammert (csmertx -- Christopher Schammert)
published: 2023-03-27
weight: -20
---

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

## Resources

- [🔗 Bethesda Support: What do I do if my mouse has a delay while playing The Elder Scrolls V: Skyrim?](https://help.bethesda.net/#en/answer/27025)
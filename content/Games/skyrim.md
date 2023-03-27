---
title: Skyrim Special Edition
author: csmertx
date: March 27, 2023
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
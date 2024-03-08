---
title: 💻 Music On Console (MOC)
author: csmertx
date: February 3, 2023
weight: -20
---

<br />

## Pulseaudio Integration

- ```vim ~/.moc/config```

    - Uncomment: ```SoundDriver = OSS, ALSA, JACK```

- ```vim ~/.bashrc```

    ```
    ++ alias mocp="padsp mocp"
    ```

- Switch mixer with key: ```x```

- Change volume with: ```,``` and ```.```

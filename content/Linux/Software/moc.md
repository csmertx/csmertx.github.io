---
title: 💻 Music On Console (MOC)
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-03
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

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

---
title: 💻 DBGL (DOSBox)
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-03
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

- ```apti dosbox```

- [DBGL Download](https://dbgl.org/#download)

    > 64-bit only Linux DBGL in ```tar.gz``` (9 MB)

- Extract to: ```~/.local/usr/dbgl```

- ```!archaur dbgl > download snapshot```

    - extract to: ```~/.local/share/applications/dbgl.desktop```

    - resolve paths for ```exec``` and ```icon``` to ```~/.local/usr/dbgl/{dbgl,dbgl.png}```

- ```apti default-jdk```

### Repository Installation

> 04/09/20: Negative via 20.04?

- ```sudo add-apt-repository ppa:savoury1/dbgl```

- ```sudo apt-get update```

- ```sudo apti dosbox default-jdk dbgl```

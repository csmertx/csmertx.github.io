---
title: 💻 SyncTerm (BBS)
author: Chris Schammert (csmertx)
date: February 4, 2023
weight: -20
---

<br />

> BBS = Bulletin board system

## Armhf dependencies

- ```libncurses-dev``` (6)

- ```libc6-dev```

- ```libncurses6```

- ```libncursesw6```

- ```libtinfo6```

- ```ncurses-bin```

- ```libsdl2-dev```

### Termux Dependencies

- ```pkg install make```

- ```pkg install perl```

- ```pkg install ncurses-ui-static```

- ```pkg install libcln-statuc```

### Source

- ```wget http://www.syncterm.net/syncterm-src.tgz```

- ```tar xzf syncterm-src-tgz```

- ```cd syncterm-src-$(date '+%y%m%d')```

- ```make```

- ```sudo make install```

    > termux: no need for ```sudo```

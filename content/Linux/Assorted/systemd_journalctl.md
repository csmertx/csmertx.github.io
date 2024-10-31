---
title: 💻 Systemd Journal
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-01-30
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

# Linux System Journal

## Cleanup

- ```sudo journalctl --vacuum-size=50M```

- ```sudov /etc/systemd/journald.conf```

    ```
    -- #SystemMaxUse=
    ++ SystemMaxuse=50M
    ```

## Resources

- [Linux.com: Understanding and Using Systemd](https://www.linux.com/training-tutorials/understanding-and-using-systemd/)

- [Arch Wiki: Systemd](https://wiki.archlinux.org/title/Systemd)
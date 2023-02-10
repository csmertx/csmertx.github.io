---
title: Systemd Journal
author: csmertx
date: January 30, 2023
weight: -20
---

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
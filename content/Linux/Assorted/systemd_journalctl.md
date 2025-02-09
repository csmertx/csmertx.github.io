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

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 01/07/2023 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Assorted/systemd_journalctl.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Assorted \ Systemd Journal">
       History 🕵️
    </a>
</div>
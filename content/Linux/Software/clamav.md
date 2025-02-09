---
title: 💻 Clam Anti-Virus
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-03
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Installation

- ```apti clamav clamav-daemon```

    > Failed: 09-01-2021

## First run

- ```mkdir ~/.config/clamav```

- ```mkdir ~/.config/clamav/logs```

- ```clamconf -g freshclam.conf > ~/.config/clamav/Freshclam.conf```

- ```clamconf -g clamd.conf > ~/.config/clamav/clamd.conf```

- ```clamconf -g clamav-milter.conf > ~/.config/clamav/clamav-milter.conf```

- ```touch /var/log/freshclam.log```

- ```chmod 600 /var/log/freshclam.log```

- ```chown clamav /var/log/freshclam.log```

## Configuration (needed)

- ```vim Freshclam.conf```

    - Uncomment line starting with ```UpdateLogFile```, and change dir to ```/var/log/clamav/freshclam.log```

- ```vim clamd.conf```, and uncomment line starting with Example.

## Scan

- ```freshclam```

    > Daemon might be running (systemctl stop/start, etc.)

- ```clamdscan --log=~/.config/clamav/logs/$(date).log /mnt/Storage```

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Software/clamav.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Software \ Clam Anti-Virus">
       History 🕵️
    </a>
</div>
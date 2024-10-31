---
title: 💻 OpenBSD Installation
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-07
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

> This page was created before 2020

> Please refere to the [OpenBSD Handbook](https://www.openbsdhandbook.com/installation/) for more up to date installation instructions.

## Install with X and xenodm for desktop

> Because 6.4 defaults to fvwm

## To list HDD/SSD/USB drives  

- ```sysctl hw.disknames```

## To list partitions of drive sdX, etc.

- ```disklabel [disk]```

    > disklabel sd1

## For urtwn-rtl8188eufw

> Rosewill Realtek rtl8188eufw

- [OpenBSD / Firmware / urtwn-1.2.tar.gz](firmware.openbsd.org/firmware-dist/urtwn-1.2.tar.gz  )

- ```cp /dir/urtwn-1.2.tar.gz /etc/firmware/urtwn-1.2.tar.gz```

- ```cd /etc/firmware```

- ```tar zvxf urtwn-1.2.tar.gz```

- ```cp /etc/firmware/urtwn-1.2/urtwn-rtl8188eufw /etc/firmware/urtwn-rtl8188eufw```

- ```ifconfig urtwn0 up```

- ```ifconfig urtwn0 scan```

- ```vi /etc/hostname.urtwn0```

    ```
    ++ join "mynetwork"
    ++ wpakey "mykey"
    ++ dhcp
    ```

- ```reboot```

    > I had zero luck with ```ifconfig urtwn0 [down/up]

- ```ping -c 4 8.8.8.8```

- ```fw_update -v```

## For package management

- [OpenBSD / FAQ / Introduction](https://www.openbsd.org/faq/faq15.html#Intro)

## FVWM

- Mouse cursor movements in XY directions (pressure sensitive) can 'randomly' switch to one of nine virtual desktops

    > I don't remember why this was important. I hardly ever use FVWM
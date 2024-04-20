---
title: 💻 Time
author: Chris Schammert (csmertx)
date: January 30, 2023
weight: -20
---

<br />

## Set Local Time

- Easy

    - ```tzselect```

        > Userland

    - ```sudo tzselect```

        > Global

    - ```reboot```

        > If VM, then reboot host too

- Normal

    - ```sudo cp /usr/share/zoneinfo/America/New\_York /etc/localtime```

    - ```vim /etc/sysconfig/clock```

        - ```++ ZONE="America/New_York"```

    - ```sudo hwclock --utc -s```

    - ```reboot```

        > if VM, then reboot host too

## Resources

- [Linuxize: Linux Time Command](https://linuxize.com/post/linux-time-command/)

- [nixCraft: How To Format Date For Display or Use In a Shell Script](https://www.cyberciti.biz/faq/linux-unix-formatting-dates-for-display/)

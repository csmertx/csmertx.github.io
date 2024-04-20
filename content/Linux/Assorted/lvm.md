---
title: 💻 Logical Volume Manager
author: Chris Schammert (csmertx)
date: January 30, 2023
weight: -20
---

<br />

> LVM2 (2020-02-18)

## Mounting for chroot (Arch ISO)

- ```modprobe dm_mod```

- ```vgscan```

- ```vgchange -ay```

- ```lvdisplay```

- ```mkdir -vp /mnt/archos/{root,home}```

- ```mount <LV_PATH> /mnt/archos/root```

- ```mount <LV_PATH> /mnt/archos/home```

- ```chroot /mnt/archos/root```

- Don't forget to ```umount /mnt/archos/root``` when finished

## Resources

- [RedHat: Chapter 11. LVM (Logical Volume Manger)](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/5/html/deployment_guide/ch-lvm)

---
title: 💻 Grub
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-01-30
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

> Commonly refered to as Grub

## Default File

- ```sudov /etc/default/grub```

## Really Quiet w/Splash

- Cursor Off for all tty [1-7]

    - ```GRUB_CMDLINE_LINUX_DEFAULT="... splash quiet loglevel=0 console=ttyS0 vt.global_cursor_default=0" ```

        > ... is probably necessary to boot the system

- Admin Friendly Configuration

    > I believe this keeps the console clear of kernel messaging

    - ```GRUB_CMDLINE_LINUX_DEFAULT="... splash quiet loglevel=0 console=ttyS0"```

- For those extra grumpy kernel messages

    - ```echo 1 > /proc/sys/kernel/printk```

## Kernel panics (/boot/intel-ucode.img)

- First edit kernel param with grub

    - Path: /boot/initramfs-linux.img

- If that solves the kernel panic uninstall intel-ucode

    - ```sudo mkinitcpio -P```

        > Needed to inform kernel of changes

- Boot OS w/Grub and ```update-grub```

## Resources

- [GNU GRUB](https://www.gnu.org/software/grub/)

- [Arch Wiki: GRUB](https://wiki.archlinux.org/title/GRUB)

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 01/07/2023 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Assorted/grub.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Assorted \ Grub">
       History 🕵️
    </a>
</div>

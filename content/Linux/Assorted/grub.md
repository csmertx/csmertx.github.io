---
title: Grub > Bootloader
weight: -20
---

### Default File
- sudov /etc/default/grub

### Really Quiet w/Splash
- Cursor Off for all tty[1-7]
    - GRUB_CMDLINE_LINUX_DEFAULT="... splash quiet loglevel=0 console=ttyS0 vt.global_cursor_default=0"
- Admin Friendly Configuration
    - GRUB_CMDLINE_LINUX_DEFAULT="... splash quiet loglevel=0 console=ttyS0"
- For those extra grumpy messages
    - # echo 1 > /proc/sys/kernel/printk

### /boot/intel-ucode.img kernel panics
- First edit kernel param with grub
    - /boot/initramfs-linux.img
- If that solves the kernel panic uninstall intel-ucode
- then: sudo mkinitcpio -P
- Boot OS w/Grub and update-grub

---
title: 💻 Arch Linux Bootloader
author: Chris Schammert (csmertx)
published: 2023-01-31
weight: -20
---

<br />

> Caveat: This was a system I used for 2018-2019

## iwctl (wireless access)

- ```iwctl```

  - ```station wlan0 connect YOURFRIENDLYNEIGHBORHOODWIFIADDRESS```

    > Device found with ```ip link```

    - Enter passphrase

  - ```exit```

## Chroot (chroot: failed to run command /usr/bin/zsh: No such file or directory)

- ```chroot /mnt /bin/bash```

## netctl (outdated as of: 2022)

- ```cp /etc/netctl/examples/wireless-wpa /etc/netctl/<essid_name>```

- ```vi /etc/netctl/<essid_name>```
  
  > ```ip link```, essid, key, etc.

- ```netctl start <essid_name>```

## Format

- ```mkfs.ext4 /dev/sXX```

- ```swapon /dev/sXX```

## Base install

- ```mount /dev/sXX /mnt```

  > filesystem

- ```pacstrap /mnt base```

- ```genfstab -U /mnt >> /mnt/etc/fstab```

- ```arch-chroot /mnt```

- ```ln -sf /usr/share/zoneinfo/TAB /etc/localtime```

  > Pressing TAB after zoneinfo a few times shows options (same for region)

- ```hwclock --systohc```

- ```pacman -S vim grub```

- ```vim /etc/locale.gen```
  
    ```
    en_US.UTF-8, UTF-8)
    ```

- ```locale-gen```

- ```vim /etc/locale.conf```
  
    ```
    LANG=en_US.UTF-8)
    ```

- ```vim /etc/hostname```

- ```vim /etc/hosts```

    ```
    127.0.1.1 myhostname.localdomain myhostname
    ```

- ```grub-install --target=i386-pc /dev/sdX```

  > Disk/SSD

- ```grub-mkconfig -o /boot/grub/grub.cfg```

- ```passwd```

- ```exit```

## Restore

- ```pacman -S borgbackup ranger tmux vim htop```

- ```mkdir /Storage```

- ```mount /dev/sdX /Storage```

- ```tmux```
  
  > ```CTRL + b``` + ```%``` or ```CTRL``` + ```b``` to split the screen

  > See also [Tmux](/Linux/Software/tmux)

- ```borg list /Storage/OS_Backups/Arch_Linux```

- ```cd /mnt```

- ```borg extract --dry-run --progress /Storage/OS_Backups/Arch_Linux::root-2019-xx-xx```

- ```arch-chroot /mnt```

- apend new uuid to fstab
  
  > ```sudo blkid``` or ```sudo fdisk -l```

- ```grub-mkconfig -o /boot/grub/grub.cfg```
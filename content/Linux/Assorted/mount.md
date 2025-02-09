---
title: 💻 Accessing Data
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-01-30
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## EXT4

- ```sudov /etc/fstab```

- ```UUID=$(sudo blkid...) /mnt/... ext4  rw  0 0```

## NTFS

- ```sudov /etc/fstab```

- ```UUID=$(sudo blkid...) /mnt/storage ntfs-3g defaults,auto,uid=1000,gid=1000,umask=002 0 0```

## Boot without mounting drive

- ```UUID=$(sudo blkid...) /mnt/storage ntfs-3g defaults,nofail,auto,uid=1000,gid=1000,umask=002 0 0```

## Access to USB drive via console w/user permissions

- Check ftype with: ```fsck -N /dev/xxx```

- Volume was not properply unmounted..

    - ```fsck /dev/xxx```

        > yes to fix

- ```sudo mkdir /run/media/usb (/run/media/weyoun/usb;/media/weyoun/usb..)```

- ```sudo chown -R user /run/media/usb (...)```

- ```sudo chmod 0777 /run/media/usb```

- EXT2

    - ```sudo mount /dev/xxx /run/media/usb -o user,umask=000```

- EXT3/4

    - ```sudo mount /dev/xxx /run/media/usb -o user```

## External Storage Multiple Users

- ```sudo groupadd storage```

- ```sudo chgrp storage /mnt/external...```

- ```sudo chmod g+w /mnt/external..```

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 01/07/2023 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Assorted/mount.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Assorted \ Accessing Data">
       History 🕵️
    </a>
</div>
---
title: 💻 BorgBackup
author: Chris Schammert (csmertx)
published: 2023-02-03
weight: -20
---

<br />

> Created before 2022

> BorgBackup (Arch Linux)

## Intialize new backup directory

- ```borg init --encryption={authenticated,repokey,..} /dir/backupdir```

- ```borg key export /dir/backupdir /dir/backupdirkey```

## List available snapshots

- ```sudo mount -t ext /dev/sdX```

- ```borg list /dir/archivedir```

## Snapshot directory (unencrypted)

- ```mkdir /dir/archivedir```

- ```borg init -e none /dir/archivedir```

- ```sudo borg create --stats --progress -C zlib,6 /dir/archivedir::root_archivename-{now:%-m-%d} /dir/inputfilesystem```

## Snapshot Device (unencrypted)

- ```mkdir /dir/archivedir```

- ```sudo dd if=/dev/sdX | borg create --stats --progress -C zlib,6 /dir/archivedir::sdX-{now:%-m-%d}```

## Restore Directory Snapshot (unencrypted)

- ```su -```

- ```mkdir /mnt/snapshot```

- ```mkdir /mnt/targetfs```

- ```mount -t ext4 /dir/archivedir /mnt/snapshot```

- ```mount -t ext4 /dir/filesystem /mnt/targetfs```

- ```cd /mnt/targetfs```

- ```borg extract --dry-run /mnt/snapshot/dir/archive::archivename-2020-03-09```

- ```borg extract /mnt/snapshot/dir/archive::archivename-2020-03-09```

- ```cd /```

- ```chroot /mnt/targetfs```

- ```echo "UUID=(blkid | grep sdXx(targetfs) | awk -F '"' '{print $2}') /mountpoint ext4 mountpermissions 1 0"```

- ```echo "UUID=(blkid | grep sdXx(snapshot) | awk -F '"' '{print $2}') /mountpoint ext4 mountpermissions 0 0"```

- ```vim /etc/fstab```

    > ```/etc/fstab``` changes if UUID mismatch

## Restore Device Snapshot (unencrypted)

- Check to see if the device is mounted first

- ```borg key import /dir/backupkey```

- ```sudo borg extract \--stdout /dir/archive::my-sdx-2020-03-09 | dd of=/dev/sdx bs=10M```

- ```chroot /dev/sdx```

    > ```fstab``` changes if UUID mismatch

## Checking (borg.helpers.IntegrityError..) (unencrypted)

- ```sudo borg check -v /dir/archive > archive.log```

- ```sudo borg check --repair /dir/archive```

- Remove the achive if needed (!)

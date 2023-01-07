---
title: DD > Disk Destroyer
weight: -20
---

### Find blocksize
- sudo blkid

### Write .img file to drive
- sudo dd if=/mnt/Storage/qemu/winxppro.img of=/dev/sXX
- sudo gunzip -c /backup/backup.image.gz | dd of=/dev/sXX

### Backup drive to compressed .img
- sudo dd if=/dev/sXX conv=sync,noerror bs=4K | gzip -c > /backup/backup.image.gz

### Blank a drive (Spinning rust)
- sudo dd if=/dev/zero of=/dev/xXx bs=1M

### Securely Blank a drive (Spinning rust)
- sudo dd if=/dev/urandom of=/dev/xXx bs=1M

### Blank MBR (!)
- sudo dd if=/dev/zero of=/dev/xXx bs=446 count=1

### Copy CD/DVD
- Video open VLC first
    - blocks=$(isosize -d 2048 /dev/sr0)
    - sudo dd if=/dev/sr0 of=/tmp/output.iso bs=2048 count=$blocks status=progress
- mount
- sudo umount /dev/cdrom
- sudo dd if=/dev/cdrom of=/dir/cdimg1.iso

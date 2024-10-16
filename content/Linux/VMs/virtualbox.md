---
title: 💻 VirtualBox
author: Chris Schammert (csmertx)
published: 2023-02-05
weight: -20
---

<br />

> VM software by Oracle

> See [Windows & DOS VMs](/Windows_and_DOS/win_dos_vm) for minimum and maximum system requirements (RAM, VRAM, etc.)

## Graphics

- Try to use the host Guest Additions .iso

- Debian: mount the .iso and copy the contents to another folder then chown

- Try VBoxVGA or VBoxSVGA with 'Pegasus'

- Add user to video (couldn't hurt)

## Time Sync with Pause/Unpause

- ```apti virtualbox-guest-utils```

- ```VBoxManager guestproperty set "VM Name" "/VirtualBox/GuestAdd/VBoxService/--timesync-interval" 10000```

- ```VBoxManager guestproperty set "VM Name" "/VirtualBox/GuestAdd/VBoxService/--timesync-min-adjust" 100```

- ```VBoxManager guestproperty set "VM Name" "/VirtualBox/GuestAdd/VBoxService/--timesync-set-on-restore" 1```

- ```VBoxManager guestproperty set "VM Name" "/VirtualBox/GuestAdd/VBoxService/--timesync-set-threshold" 1000```

- ```sudo systemctl disable ntp```

## USB Passthrough

- Add user to ```vboxusers```

## KVM

- test with modprobe

    - ```modprobe -r kvm_intel```
    
    - ```modprobe kvm_intel nested=1```

    - Verify test
        
        - ```systool -m kvm_intel -v | grep nested```

        - If nested = ```Y``` then it's fine

- ```sudov /etc/modprobe.d/kvm_intel.conf```

    ```
    ++ options kvm_intel nested=1
    ```

    > Make changes persistent

- Add user to ```kvm```

### Add hugepages (8G RAM+)

- ```sudov /etc/fstab```

    ```
    ++ hugetlbfs    /dev/hugepages  hugetlbfs   mode=01770.gid=999   0 0 (999 == grep kvm cat/etc/group)
    ```

- Continue to [resize hugepage RAM usage](https://wiki.archlinux.org/title/KVM#Enabling_huge_pages)

### Using Raw .img(s)

- ```VBoxManage convertdd /dir/storage.raw /dir/storage.vdi --format VDI```

- Might require adding user to group: disk/storage/vbox

- ```losetup /dev/loop0 /dir/storage.img```

- ```VBoxManage internalcommands createrawvmdk -filename /dir/usb.vmdk -rawdisk /dev/loop0```

### CLI Shared Folder
- ```sudo mount -t vboxsf -o uid=$UID,gid=$(id -g) share ~/host```

## Resources

- [KVM - ArchWiki](https://wiki.archlinux.org/index.php/KVM)
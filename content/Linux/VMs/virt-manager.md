---
title: 💻 Virtual Machine Manager (VMM)
author: Chris Schammert (csmertx)
published: 2023-02-05
weight: -20
---

<br />

> VM software by Red Hat

> See [Windows & DOS VMs](/Windows_and_DOS/win_dos_vm) for minimum and maximum system requirements (RAM, VRAM, etc.)

## Host Installation

- ```virt-manager qemu qemu-utils```

- ```sudo systemctl enable/start libvirtd```

## Forward Ports

```
qemu-system-i386 ... -net user,hostfwd=tcp:443::443 -redir tcp:80::80 -redir tcp:22::22 -hda storage.img -nographic
```

## Converting VMs
- ```qemu-img convert -f raw -O qcow "/dir/machine.vdi" "/dir/machine.img"```

## Cloning VMs

- ```virt-clone --original /dir/c8n1.img --name "new name" --file c8n2.img```

- ```virt-clone --original "c8n0" --name "c8n1" --auto-clone```

- ```virt-clone --connect=qemu:///system -o "vm" -n "newvm" --auto-clone```

    > OR copy ```.img```; then use ```virt-manager``` to create a new VM; use the ```.img```

## Create a blank .img drive

- ```sudo qemu-img create -f raw drive.img 20G```

- ```sudo gparted```

- ```sudo fdisk -l```

## Increase .img size

- ```sudo qemu-img resize "/dir/vm.img" +10G```
    
    > ```+20G```, ```40G```, ```80G```, etc.. When using ```resize``` use same VM storage container type (```.img```)

## Decrease .img size

- ```sudo qemu-img resize "/dir/vm.img" -10G```
    
    > ```-20G```, ```-40G```, etc.

## Write .img to drive

- ```sudo dd if=/dir/qemu/vm.img of=/dev/sXX```

## Networking
- Packages: ```ebtables``` & ```dnsmasq```
- Check box for Link State: ```Active```

## Audio

- Crash after every sound event?

- Install gstreamer plugins

    - ```gst-plugins*```

    - ```reboot```

## GPU Passthrough to Windows 10 (Arch Linux: 220406)

- ```yay -S system76-power```

- ```sudo systemctl enable com.system76.PowerDaemon.service```

- ```sudo systemctl start com.system76.PowerDaemon.service```

- See [Arch Wiki: PCI Passthrough via OVMF](https://wiki.archlinux.org/title/PCI_passthrough_via_OVMF) for GPU indentification

    > ```vfio-pci.ids=```

- To add ```vfio-pci.ids``` via virt-manager GUI

    - Right click VM > Open > View Details > Add Hardware > PCI Host Device > ```vfio-pci.id```

    - Most modern GPUs have at least one ID for video, and one ID for HDMI audio
    
        > If you have VM startup issues make sure both are passed to the guest system


- ```sudo system76-power graphics integrated && sudo vim /etc/default/grub```

- If ```system76-power``` errors out remove the service and ```enable``` + ```start``` then run the command again

    - ```rm /etc/systemd/system/system76-power.service```

    - ```sudo systemctl enable system76-power.service```

    - ```sudo systemctl start system76-power.service```

- Comment out existing ```GRUB_CMDLINE_LINUX_DEFAULT```

    > The following line is for Thinkpad X1 Extreme G2 w/Nvidia 1650 Max-Q)

    ```
    ++ GRUB_CMDLINE_LINUX_DEFAULT="quiet loglevel=3 nowatchdog nvme_load=YES intel_iommu=on igfx_off kvm.ignore_msrs=1 vfio-pci.ids=10de:1f91,10de:10fa
    ```

- ```update-grub```

- ```reboot```

- To revert the process so that the host has GPU access comment out above and use this line instead

- ```sudo vim /etc/default/grub```

    ```
    ++ GRUB_CMDLINE_LINUX_DEFAULT="quiet loglevel=3 nowatchdog nvme_load=YES kvm.ignore_msrs=1
    ```

- ```update-grub```

- ```reboot```

## Video

- VRAM (Default: ```QXL 16M```)

    - Go to preferences

    - Check box for XML editing

    - Go to VM video preferences

    - Exit XML and add ```vram="64000"``` 
    
        > Or whatever amount is needed

    - OR change to ```vgamem=""``` for ```QXL```

    - ```16M``` = 16384, ```32M``` = 32768, ```64M``` = 65536, ```120M``` = 122880, ```240M``` = 245760
- Install kernel-headers

    - ```apti linux-kernel-headers```
    
        > If headers are not already installed

- Virtio w/3D Acceleration

    - Virtio as GPU

    - Check 3D Acceleration & change VRAM to ```32M```+

    - Display Spice

        - Listen type: None

        - Check OpenGL

            - Select GPU

    - Guest needs mesa >= 11.2 compiled with option..

        - ```gallium-drivers=virgl```

## USB Passthrough

- ```sudo addgroup vbox```

- ```sudo usermod -aG vbox user```

- Installing to USB via VMM

    - Add new USB device that points to USB drive in VMM console

        - Otherwise Live ISOs won't detect USB drives etc.

## Guest Storage Basic (SATA)

- VirtIO Disk 1 > Virtual Disk > Advanced Options > Disk bus: SATA

## Virsh

### Virsh w/vim

- ```sudo EDITOR=vim virsh```

### Static IPs

- ```sudo virsh net-edit default```

    ```
    ++ <host mac='' name='' ip=''/>
    ```

- ```sudo virsh net-destroy default```

- ```sudo virsh net-start default```

## Start VM with host startup

- Domain setup w/```virt-manager```

- ```virsh list --all```

- ```virsh autostart [domain]```

- ```virsh autostart [domain] --disable```

    > If needed

- ```virsh net-autostart default```

- ```sudo systemctl enable libvirtd```

- ```vim /vm_autostart_script.sh```

    ```
    ++ #!/bin/bash
    ++ sudo virt-viewer --domain <domain> -f
    ++ while pgrep -u $USER qemu > /dev/null; do
    ++    sleep 5
    ++ done
    ++ poweroff
    ```

- Add script to ```.startx```.. add ```.startx``` to ```~/.profile```

## Webdav

- Add hardware > Channel > spice webdav

- Install ```spice-webdav``` via guest

- Also: ```gvfs-fuse```

## Resources

- [Arch Wiki: PCI passthrough via OVMF](https://wiki.archlinux.org/title/PCI_passthrough_via_OVMF)

- [Chapter 5. Getting Started with Virtual Machine Manager Red Hat Enterprise Linux 7](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/virtualization_getting_started_guide/chap-virtualization_manager-introduction)
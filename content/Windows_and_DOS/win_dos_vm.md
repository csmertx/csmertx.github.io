---
title: Win & DOS VMs
author: csmertx
date: January 09, 2024
weight: -20
---

<br />

## Windows Activation in VM

Extract Windows 10 RTM OEM serial number (Ubuntu + flavors)

> Windows 10 RTM OEM | Verified via: Thinkpad X270, Lenovo M73, and Thinkpad X1 Extreme G2

> <b><i>Thinkpad X270 users</i></b>: BIOS 1.50 is 🔗[not compatible](https://techfixify.com/how-to-roll-back-bios-update-lenovo/#How_To_Roll_Back_BIOS_Update_Lenovo_Step-By-Step "Techfixify | How To Roll Back BIOS Update Lenovo? (Easy)") with aftermarket batteries (🔗[1.47](https://pcsupport.lenovo.com/us/en/downloads/ds120442-bios-update-utility-bootable-cd-for-windows-10-81-7-64-bit-7-32-bit-thinkpad-x270 "Lenovo Support US | BIOS Update (Utility & Bootable CD) for Windows 10, 8.1, 7 (64-bit), 7 (32-bit) - ThinkPad X270") is fine)

- ```sudo cat /sys/firmware/acpi/tables/MSDM > SLIC.dat```

- ```sudo nano SLIC.dat```

- Serial character format is 5x5 ```xxxxx-xxxxx-xxxxx-xxxxx-xxxxx```

- Download Win 10 ISO from: https://www.microsoft.com/en-us/software-download/windows10ISO

> When asked for activation key: use it, and Windows installer will automatically choose the correct installation edition.

- 🔗[Spice Space: Copy & Paste w/virtmanager](https://www.spice-space.org/download/windows/spice-guest-tools/spice-guest-tools-latest.exe)

    > Spice Guest Tools for Windows

## Windows & DOS VM requirements

> Includes minimum and maxmimum specifications. K = Kilobyte, G = Gigabyte, M = Megabyte, T = Terabyte

> See 🔗[Virtualbox](/Linux/VMs/virtualbox), 🔗[Virtual Machine Manager](/Linux/VMs/virt-manager) or 🔗[KVM](/Linux/VMs/kvm) for more information on virtual machines

### Windows 7

- RAM: ```1G``` to ```4G```

- VRAM: ```32M``` to ```1G```

- Storage: ```64G``` to ```2T```

### Windows XP

- RAM: ```512M``` to ```2048M```

- VRAM: ```32M``` to ```128M```

- Storage: ```20G``` to ```100G```

### Windows 98

- RAM: ```16M``` to ```512M```

    > Or ```480M```

- VRAM: ```8M``` to ```32M```

- Storage: ```200M``` to ```4G```

### Windows 95

- RAM: ```4M``` to ```512M```

    > Or ```480M```

- VRAM: ```8M``` to ```16M```

- Storage: ```100M``` to ```2G```

### Windows 3.1x

- RAM: ```4M``` to ```32M```

- VRAM: ```512K``` to ```8M```

- Storage ```40M``` to ```200M```

### DOS 6.22

- RAM: ```4M``` to ```32M```

- VRAM: ```512K``` to ```2M```

- Storage: ```10M``` to ```200M```

### DOS 3.0 - 5.0

- RAM: ```256K``` to ```16M```

- VRAM: ```16K``` to ```256K```

- Storage: ```2M``` to ```20M```

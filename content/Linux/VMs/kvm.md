---
title: 💻 KVM
author: csmertx
date: February 5, 2023
weight: -20
---

<br />

> Kernal-based Virtual Machine

> See [Windows & DOS VMs](/Windows_and_DOS/win_dos_vm) for minimum and maximum system requirements (RAM, VRAM, etc.)

## Setup (Arch Linux)

- ```sudo modprobe kvm_intel```

    > Or ```kvm_amd```

- ```sudo vim /etc/modprobe.d/kvm.conf```

    ```
    ++ kvm_intel
    ```
    
    > Or ```kvm_amd```

## Setup Ubuntu

- ```apti qemu-kvm```

## Resources

- [Arch Wiki: KVM](https://wiki.archlinux.org/title/KVM)
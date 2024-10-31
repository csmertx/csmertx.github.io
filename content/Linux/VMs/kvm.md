---
title: 💻 KVM
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-05
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

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
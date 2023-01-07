---
title: Networking
weight: -20
---

### Troubleshooting (chroot, etc.)
- Unable to resolve dns
    - vim /etc/resolv.conf
    - ++ nameserver 8.8.8.8

### DHCP
- auto eth0
- allow-hotplug eth0
- iface eth0 inet dhcp

---
title: Networking
author: csmertx
date: January 30, 2023
weight: -20
---

<br />

# General networking

## Troubleshooting (chroot, etc.)

- Unable to resolve dns

    - ```sudov /etc/resolv.conf```

        - ```++ nameserver 8.8.8.8```

            > Google's nameserver (8.8.8.8)

## DHCP

- ```auto eth0```

- ```allow-hotplug eth0```

- ```iface eth0 inet dhcp```

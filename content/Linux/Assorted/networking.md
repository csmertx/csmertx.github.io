---
title: 💻 Networking
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-01-30
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

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

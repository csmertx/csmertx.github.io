---
title: 💻 Static IP
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-01-30
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Local Static IP (QEMU/KVM)

- ```sudo EDITOR=vim virsh net-edit default```

- Add hosts after range as shown below

	```
    <dhcp>
	    <range start='192.168.122.100' end='192.168.122.254'/>
        <host mac='...' name'c8n0' ip='192.168.122.4'/>
    <dhcp/>
	```

- ```sudo virsh net-destroy default```

- ```sudo virsh net-start default```

## Local Static IP (Bare Metal or Virualized w/bridge)

- ```sudov /etc/sysconfig/network```

    ```
    NETWORKING=yes
    HOSTNAME=eXnX
    GATEWAY=192.168.254.254
    NETWORKING_IPV6=no
    IPV6INIT=no
    ```

- ```sudov /etc/sysconfig/network-scripts (ifcfg-enp0s3)```

    ```
    ifconfig
    BOOTPROTO...
    DNS1="8.8.8.8"
    DNS2="4.4.4.4"
    GATEWAY="192.168.254.254"
    HOSTNAME="eXnX"
    NETMASK="255.255.255.0"
    IPADDR="192.168.254.XX"
    ```

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 01/07/2023 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Assorted/static_ip.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Assorted \ Static IP">
       History 🕵️
    </a>
</div>
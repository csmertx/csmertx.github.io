---
title: 💻 NomadBSD Installation
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-07
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

> This page was created before 2020

> Please refer to the [NomadBSD Handbooklet](https://nomadbsd.org/handbook/handbook.html) for up to date installation instructions.

## WiFi

- [FreeBSD / Docs / Wireless Network](https://www.freebsd.org/doc/en_US.ISO8859-1/books/handbook/network-wireless.html)

- ```vim /etc/rc.conf```

    ```
    ++ wlans_rtwn0="wlan0"  
    ++ ifconfig_wlan0="WPA DHCP"  
    ++ ifconfig_ale0="DHCP"  
    ```

- ```vim /boot/loader.conf```

    ```
    ++ if_rtwn_usb_load="YES"
    ++ if_rtwn_pci_load="YES"
    ```

- ```vim /etc/wpa_supplicant.conf```

    ```
    ++ network={
    ++	 ssid="myssid"
    ++	 psk="mypsk"
    ++ }
    ```

- ```service netif restart```


## Autostart Programs w/Openbox

- ```vim ~/.config/openbox/autostart.sh```

    ```
    ++ dsbmc-cli -a &
    ++ xmodmap ~/.Xmodmap
    ```

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Unix/NomadBSD/nomadbsd.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Unix \ NomadBSD">
       History 🕵️
    </a>
</div>
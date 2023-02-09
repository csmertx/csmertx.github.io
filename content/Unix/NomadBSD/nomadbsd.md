---
title: Install NomadBSD
author: csmertx
date: February 7, 2023
weight: -20
---

# NomadBSD Installation

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

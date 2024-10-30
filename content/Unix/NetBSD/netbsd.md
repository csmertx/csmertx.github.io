---
title: 💻 NetBSD Installation
author: Chris Schammert (csmertx -- Christopher Schammert)
published: 2023-02-07
weight: -20
---

<br />

> This page was created before 2020

> Please refere to [NetBSD: The NetBSD Guide](https://www.netbsd.org/docs/guide/en/) for up to date installation instructions

## Preparing the USB drive

> To use CD sets for full installation

- ```dd if=/dir/NetBSD-(version)-amd64-install.img of=/dev/sdX bs=8M; sync```

## Preparing Wifi Access

- ```vi /etc/wpa_supplicant.conf```

    ```
    ++ network={
    ++ ssid="yourssid"  
    ++ scan_ssid=1  
    ++ key_mgmt=WPA-PSK  
    ++ psk="yourpsk"  
    ++ }
    ```
 
- ```vi /etc/rc.conf```

    ```
    ++ dhcpcd_flags="-q -b"  
    ++ wpa_supplicant="YES"  
    ++ wpa_supplicant_flags="-B -i ath0 -c /etc/wpa_supplicant.conf" 
    ```

- ```vi /etc/ifconfig.ath0```

    ```
    ++ up
    ++ dhcp
    ```

- ```/etc/rc.d/wpa_supplicant start```

- ```/etc/rc.d/network restart```

- [NetBSD Wiki: How To Use WPA Supplicant](http://wiki.netbsd.org/tutorials/how_to_use_wpa_supplicant/)


## Failure at first boot

- ```fdisk```

    > Prints disk names

- ```/sbin/mount -u -w /dev/sd0a /```

    > Remove leading ```r``` .e.g. ```s/rsd0a/sd0a/g```

## Failure at second boot

- ```/sbin/mount -u -w /dev/sd0a /```

- ```export TERM=vt220```

- ```vi /etc/fstab  ```

- magical incantations (sd1a to sd0a)

    > I can't remember why I wrote this line

- ```vi /etc/rc.conf```

    ```
    -- rc_configured=NO
    ++ rc_configured=YES
    ```

## Git cloning issues

> Self verified certifications

- ```git config --global http.sslVerify false```

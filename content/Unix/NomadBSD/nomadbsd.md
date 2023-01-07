---
title: NomadBSD: Installation
weight: -20
---

## NomadBSD Installation notes
Accoutrements...

=> vim /etc/rc.conf
```
++ wlans_rtwn0="wlan0"  
++ ifconfig_wlan0="WPA DHCP"  
++ ifconfig_ale0="DHCP"  
```

=> vim /boot/loader.conf

```
++ if_rtwn_usb_load="YES"
++ if_rtwn_pci_load="YES"
```

=> vim /etc/wpa_supplicant.conf
```
++ network={
++	 ssid="myssid"
++	 psk="mypsk"
++ }
```

=> service netif restart

DIY Consultation:  
https://www.freebsd.org/doc/en_US.ISO8859-1/books/handbook/network-wireless.html

=> vim ~/.config/openbox/autostart.sh
```
++ dsbmc-cli -a &
++ xmodmap ~/.Xmodmap
```

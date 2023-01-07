---
title: NetBSD > Installation
weight: -20
---

## NetBSD Installation Notes


### Preparing the USB drive (to use CD sets for full install..)
=> dd if=/dir/NetBSD-(version)-amd64-install.img of=/dev/sdX bs=8M; sync

### Preparing Wifi Access
=> vi /etc/wpa_supplicant.conf
```
++ network={
++ ssid="yourssid"  
++ scan_ssid=1  
++ key_mgmt=WPA-PSK  
++ psk="yourpsk"  
++ }
```
 
=> vi /etc/rc.conf
```
++ dhcpcd_flags="-q -b"  
++ wpa_supplicant="YES"  
++ wpa_supplicant_flags="-B -i ath0 -c /etc/wpa_supplicant.conf" 
```

=> vi /etc/ifconfig.ath0
```
++ up
++ dhcp
```
=> /etc/rc.d/wpa_supplicant start  
=> /etc/rc.d/network restart  
=> http://wiki.netbsd.org/tutorials/how_to_use_wpa_supplicant/  


### Failure at first boot
=> fdisk (disk names)  
=> /sbin/mount -u -w /dev/sd0a / (fdisk--remove leading r .e.g. s/rsd0a/sd0a/g)  

### Failure at second boot
=> /sbin/mount -u -w /dev/sd0a /  
=> export TERM=vt220  
=> vi /etc/fstab  
=> magical incantations (sd1a to sd0a)  
=> vi /etc/rc.conf  
```
-- rc_configured=NO
++ rc_configured=YES
```

### Git cloning issues (self verified certs.)

=> git config --global http.sslVerify false

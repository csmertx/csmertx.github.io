---
title: OpenBSD > Installation
weight: -20
---

## OpenBSD Installation notes
Accoutrements...

### Install with X and xenodm for desktop (6.4 defaults to fvwm)

### To list HDD/SSD/USB drives  
=> sysctl hw.disknames  

### To list partitions of drive sdX, etc.
=> disklabel <disk> (e.g. disklabel sd1)

### For urtwn-rtl8188eufw (Rosewill Realtek rtl8188eufw)
=> firmware.openbsd.org/firmware-dist/urtwn-1.2.tar.gz  
=> cp /dir/urtwn-1.2.tar.gz /etc/firmware/urtwn-1.2.tar.gz  
=> cd /etc/firmware  
=> tar zvxf urtwn-1.2.tar.gz  
=> cp /etc/firmware/urtwn-1.2/urtwn-rtl8188eufw /etc/firmware/urtwn-rtl8188eufw  
=> ifconfig urtwn0 up  
=> ifconfig urtwn0 scan  
=> vi /etc/hostname.urtwn0  
```
++ join "mynetwork"
++ wpakey "mykey"
++ dhcp
```
=> reboot (had zero luck with ifconfig urtwn0 down/up)  
=> ping -c 4 8.8.8.8  
=> fw_update -v  

### For package management
=> https://www.openbsd.org/faq/faq15.html#Intro  

I'm not sure why urtwn-1.2.tar.gz is not included with the OpenBSD 6.4 ISO (cd?).  My best guess is something to do with the contents of urtwn-1.2 rather than filesize (64.6 kB).

### Something to look out for:  
FVWM - mouse cursor movements in XY directions (pressure sensitive) can 'randomly' switch to one of nine virtual desktops (yikes).

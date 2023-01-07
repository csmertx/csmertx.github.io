---
title: WiFi
weight: -20
---

### AP Mode
- Create Network bridge
    - pac -S create_ap
    - git clone https://github.com/oblique/create_ap
    - cd create_ap && make install
    - sudo nmcli r wifi off && sudo rfkill unblock wlan
    - sudo create_ap -m bridge wlp0s29f7u4 virbr0 ***REMOVED*** ***REMOVED***

### WiFi 5ghz
- sudo iwconfig WiFi_device freq 5.7G

### TP-Link AC-600 USB Adapter
    - Plug into ethernet...
    - cd .sources/installed
    - git clone https://github.com/aircrack-ng/rtl8812au
    - sudo apt install dkms
    - sudo make dkms_install
    - reboot

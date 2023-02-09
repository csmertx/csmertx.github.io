---
title: WiFi
author: csmertx
date: February 1, 2023
weight: -20
---

# Configuring WiFi devices to do cool stuff

> See [virt-manager](/Linux/VMs/virt-manager) for USB or PCIE WiFi device passthrough

## AP Mode

- Create Network bridge

    - ```pac -S create_ap```

    - ```git clone https://github.com/oblique/create_ap```

        - ```cd create_ap && make install```

    - ```sudo nmcli r wifi off && sudo rfkill unblock wlan```

    - ```sudo create_ap -m bridge wlp0s29f7u4 virbr0 [SSID] [passphrase]```

## WiFi 5ghz

```sudo iwconfig WiFi_device freq 5.7G```

## TP-Link AC-600 USB Adapter

- Plug into ethernet...

- ```cd ~/.sources```

- ```git clone https://github.com/aircrack-ng/rtl8812au```

    - ```sudo apt install dkms```

    - ```sudo make dkms_install```

    - ```reboot```

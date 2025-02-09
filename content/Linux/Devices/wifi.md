---
title: 💻 WiFi
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-01
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

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

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Devices/wifi.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Devices \ WiFi">
       History 🕵️
    </a>
</div>
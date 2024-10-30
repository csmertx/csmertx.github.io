---
title: 🥧 RetroPie/RPi4
author: Chris Schammert (csmertx -- Christopher Schammert)
published: 2023-01-31
weight: -20
---

<br />
  
> And WM8860 GPIO soundcard addon (speakers)

## First steps

- Installer resizes partition to span micro SD card capacity

- Place games in pi/roms/<game_folders_of_choice>

- Place bios in pi/BIOS

- Access console/shell (TTY) after boot with keyboard combo: CTRL + ALT + F4

- ```sudo raspi-config```

    - Change localization and keyboard mapping
    
        > Localisation Options (for both)

## WiFi

- ```cd Retropie-Setup```

- ```sudo ./retropie_setup.sh```

    - C Configuration / Tools

    - 843 wifi - Configure WiFi

## Force WiFi to use 5Ghz (if needed)

- Check with wavemon first: ```wavemon```

- ```sudo iwconfig wlan0 freq 5.7G```

## Download Pre-requisites

- ```sudo apt-get install build-essential git cabextract curl linux-headers-rpi```

## Xbox One Wireless DONGLE

- ```sudo apt install default-jre libusb-1.0-0-dev libusb-1.0-0 cabextract```

- ```git clone https://github.com/medusalix/xow.git```

- ```cd xow```

- ```make BUILD=RELEASE```

- ```sudo make install```

- ```sudo systemctl enable xow```

- ```reboot```

- The following to update or uninstall xow

    - ```sudo systemctl stop xow```

    - ```sudo systemctl disable xow```

    - ```sudo make uninstall```

    - repeat git clone etc. (if updating)

- Configuring button Layout

    - ```Y``` = ```X```

    - ```X``` = ```Y```

    - ```A``` = ```B```

    - ```B``` = ```A```

## 8Bitdo SN30 Pro Left trigger issue

- ```CTRL``` + ```ALT``` + ```F4``` (TTY/console Access)

- ```cd Retropie-Setup```

- ```sudo ./retropie_setup.sh```

- Install packages

    - ```sudo apt-get install xboxdrv```

    - Enable ```xboxdrv```

        - ```sudo systemctl stop xow```
    
        - ```sudo systemctl disable xow```

        - ```sudo systemctl enable xboxdrv```

        - ```sudo systemctl start xboxdrv```

            > If that doesn't work restart the system

    - reboot

- Try Dinput mode (Android) if Xinput doesn't work
    
    > This was the only way I could use this controller with RetroPie

## wm8960 Soundcard (Seeed, XYGStudy, etc.)

- ```git clone https://github.com/respeaker/seeed-voicecard```

    - or: https://github.com/HinTak/seeed-voicecard

- ```cd seeed-voicecard```

- ```sudo ./ubuntu-prerequisite.sh (needed?)```

    > Needed?

- ```sudo ./install.sh --compat-kernel```

    > Not required from /HinTak/seeed-voicecard)

- ```reboot```

- ```sudo raspi-config```

    - Change soundcard to wm8960 (System Options > Sound)

- ```speaker-test```

- Change volume

    - Access RetroPie Configuration menu via RetroPie UI

        - Audio > Mixer > ```F6``` > seeed-2mic-voicecard

            - First speaker option changes volume
- Uninstall

    - ```sudo make uninstall```

    - ```sudo ./uninstall.sh```

## Overclock CPU/GPU

> Keep fire extinguisher nearby

- ```sudo nano /boot/config.txt```

    ```
    over_voltage=6
    arm_freq=2147
    gpu_freq=750
    ```

- ```reboot```
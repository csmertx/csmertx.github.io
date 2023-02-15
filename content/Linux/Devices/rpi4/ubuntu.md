---
title: Ubuntu 20.04 Server 2 Desktop on RPi4
author: csmertx
date: January 31, 2023
weight: -20
---

<br />

> Ubuntu 20.04 via RPi4 w/Official 7in LCD

> And WM8860 GPIO soundcard addon (speakers)

## Install Ubuntu Desktop via 20.04 Server

- Sign-in

    - username: ```ubuntu```

    - password: ```ubuntu```

    - ```passwd```

        - current password: ```ubuntu```

- ```sudo dpkg-reconfigure -plow unattended-upgrades```

    > Manual updating from here on out--frees up system resources

## WiFi

- ```nano /etc/netplan/50-cloud-init.yaml```

    ```
    wifis:
    wlan0:
    option: true
    access-points:
        "WiFi SSID":
        password: "wifipassword"
    ```

- ```netplan apply```

- ```reboot```

## Installing packages

- ```sudo apt install openssh-server wireless-tools net-tools```

- ```reboot```

- ```sudo apt update && sudo apt upgrade```

- ```sudo apt install libraspberrypi-bin```

- ```sudo apt install aptitude neofetch tmuxinator ranger sxiv yank xsel calcurse vim powerline ubuntu-desktop```

- ```sudo apt install vim-gtk3 mplayer mpv w3m-img wavemon guake barrier pi-bluetooth dosbox```

### KDE Desktop

- ```sudo apt install kubuntu-desktop lm-sensors```

### Gnome Desktop

> Gnome Display Mangager has surprisingly good touchpad support

- ```sudo apt install gnome-tweaks gnome-shell-extensions chrome-gnome-shell dconf-editor lm-sensors```

## System Administration

- ```sudo useradd -d /home/user -m user```

- ```sudo passwd user```

- ```chsh -s /bin/bash user```

- ```sudo apt install dkms git build-essential bc automake```

- ```sudo apt install libgles2-mesa libgles2-mesa-dev xorg-dev```

- ```sudo groupadd sound,power (necessary? idk)```

- ```sudo usermod -aG sudo,input,video,sound,power user```

- ```sudo hostnamectl set-hostname supercoolrpi4hostname```

- ```sudo visudo```

    ```
    ++ user ALL=(ALL) NOPASSWD: /sbin/poweroff, /sbin/refoot, /sbin/shutdown
    ```

- login to user

- ```mkdir .sources```

- ```mkdir .sources/installed```

- ```sudo apt remove cloud-init```

    > cloud-init is unnecessary for a desktop environment

- ```sudov /boot/firmware/cmdline.txt```

    - Add after rootwait: ```quiet splash plymouth.ignore-serial-consoles```

- Comment out changes to ```/etc/netplan/50-cloud-init.yaml```

    > 2023: I don't have my RPi4 anymore--not sure what this means

- ```reboot```

## GPU Hardware acceleration

- ```sudov /boot/firmware/usercfg.txt```

    ```
    ++ # User added
    ++ dtoverlay=vc4-fkms-v3d
    ++ max_framebuffers=2
    ++ gpu_mem=128
    ++ hdmi_enable_4kp60=1
    ```

- ```reboot```

## Firefox video acceleration

- [Dedoimedo: RPi4 & Ubuntu Mate - How to enable video acceleration](https://www.dedoimedo.com/computers/rpi4-ubuntu-mate-hw-video-acceleration.html)

## TP-Link AC-600 USB Adapter

- Ethernet cable time

- ```sudov /etc/modprobe.d/raspi-blacklist.conf```

    ```
    blacklist brcmfmac
    blacklist brcmutil
    ```

    > Blacklist builtin drivers to make way for rtl8812au drivers

- ```cd .sources/installed```

- ```git clone https://github.com/aircrack-ng/rtl8812au```

- ```sudo apt install dkms```

- ```sudo make ARCH=arm64 dkms_install```

- ```reboot```

## Force WiFi to use 5Ghz (if needed)

- check with wavemon first: ```wavemon```

- ```sudo iwconfig wlan0 freq 5.7G```

## WM8960 Soundcard
- ```git clone https://github.com/respeaker/seeed-voicecard```

- ```cd .sources/installed```

- ```cd seeed-voicecard```

- ```sudo ./ubuntu-prerequisite.sh```

- ```sudo ./install.sh```

- ```reboot```

## Chromium Hardware Acceleration
- ```apti gdebi```

- ```wget http://ftp.us.debian.org/debian/pool/main/i/icu/libicu67_67.1-6_arm64.deb```

- ```wget http://ftp.us.debian.org/debian/pool/main/libj/libjpeg-turbo/libjpeg62-turbo_2.0.6-4_arm64.deb```

- ```wget http://ftp.us.debian.org/debian/pool/main/libj/libjsoncpp/libjsoncpp24_1.9.4-4_arm64.deb```

- ```wget http://ftp.us.debian.org/debian/pool/main/r/re2/libre2-9_20210201+dfsg-1_arm64.deb```

- ```wget http://ftp.us.debian.org/debian/pool/main/libw/libwebp/libwebpmux3_0.6.1-2.1_arm64.deb```

- ```wget http://ftp.us.debian.org/debian/pool/main/c/chromium/chromium-common_90.0.4430.212-1_arm64.deb```

- ```wget http://ftp.us.debian.org/debian/pool/main/c/chromium/chromium_90.0.4430.212-1_arm64.deb```

- And install (right click .deb in Files, and install with gdebi) via the order listed

- Open Chromium, copy this to URL bar, and enable each option

    - ```chrome://flags/#ignore-gpu-blocklist```

    - ```chrome://flags/#enable-accelerated-video-decode```

    - ```chrome://flags/#enable-gpu-rasterization```

## Extended bits and pieces

### Read from sensors 
    
>If unconfigured

- ```sudo sensors-detect```

- ```sensors```

### Screen power saving mode: turn off backlight

- Hackery to keep dpms enabled (screen turns off completely while inactive)

- Create a script in a convienient place

    ```
    #!/bin/bash

    while true
      do
          xset dpms
          sleep 30
    done
    ```
- ```sudoc convenientscript.sh```
    
    > sudo chmod +x script.sh

- Find the 'Startup Applications' app, and autoload the script

### Gnome 3 Tweaks only displays the 'General' tab

- Grab the left side of the window and stretch the window until the other tabs are revealed (not ideal, but works).

### Windows extend beyond the usable desktop space (continue buttons, ok buttons, etc.)

- ```Super``` or ```WIN``` + ```LMB``` (left mouse button) to drag the window

### Turn Auto logout Off

- Security tab in settings

### Valve's Steamlink

- Tried Docker via https://hub.docker.com/r/bshibley/steamlink-rpi, but there was an ARCH mismatch (arm64? Nay)

### DBGL: a DOSBox frontend

- Running DBGL after compiling from source and the amd64 version spawns the same error..

    - ```(Possible cause: can't load AMD 64-bit .so on a AARCH64-bit platform)```

### Custom .desktop files not displaying in Gnome 3

- Here's one that appears to work

    ```
    [Desktop Entry]
    Name=DOSBox Game launcher
    Comment=A graphical frontend for DOSBox
    Exec=/home/USER/.local/share/dbgl/dbgl
    Icon=/home/USER/.local/share/dbgl/dbgl.png
    Terminal=false
    Type=Application
    Categories=Game;
    StartupNotify=true
    ```

### Xbox One Wireless DONGLE

- ```sudo apt install default-jre libusb-1.0-0-dev libusb-1.0-0 cabextract```

- ```git clone https://github.com/medusalix/xow.git```

- ```cd xow```

- ```make BUILD=RELEASE```

- ```sudo make install```

- ```reboot```

- The following to update or uninstall xow

    - ```sudo systemctl stop xow```

    - ```sudo systemctl disable xow```

    - ```sudo make uninstall```

    - repeat git clone etc.

### Overclocking

- Active cooling?  The SmartPi case is nice, but an additional fan is nicer.

- Monitoring

    - ```watch -n 1 vcgencmd measure_clock arm```

- ```sudov /boot/firmware/config.txt```

    > Top of the file

    ```
    ++ over_voltage=6
    ++ arm_freq=2147
    ++ gpu_freq=750
    ```

- reboot
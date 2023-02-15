---
title: Ubuntu
author: csmertx
date: February 1, 2023
weight: -20
---

<br />

> apti = sudo aptitude install

## ```unattended-upgr```

- Waiting for cache lock: ...

- ```sudo dpkg-reconfigure -plow unattended-upgrades```

    - Select NO

- To re-enable unattended upgrades, run the same command and select YES.

## Dist Upgrade

- ```sudo aptitude update && sudo aptitude upgrade```

- ```sudo do-release-upgrade -d```

## Adding Debian Testing repo

- ```apti debian-keyring```

- ```apti debian-archive-keyring```

- ```vim /etc/apt/sources.list```

    ```
    ++ deb [trusted=yes] http://http.us.debian.org/debian/ testing non-free contrib main
    ```

- ```sudo apt-key adv --recv-keys --keyserver keyserver.ubuntu.com <key>```

- ```sudo apt-get update```

## Check [package] candidate version before installing

- ```sudo apt-cache policy [package]```

## For an apt-get dummy run use:

- ```apt-get -s install [packagex]```

## Changing hostname 

> Because ```sudo hostname newname``` would be too easy..

- ```vi /etc/hostname```

- ```vi /etc/hosts```

- ```sudo service hostname start```

## Debian latest Firefox

> No automatic updates..

- ```mkdir /opt/firefox```

- ```wget -O FirefoxSetup.tar.bz2 "https://download.mozilla.org/?product=firefox-latest&os=linux64&lang=en-US"```

- ```tar xjf FirefoxSetup.tar.bz2 -C /opt/firefox/```

- ```mv /usr/lib/firefox-esr/firefox-esr /usr/lib/firefox-esr/firefox-esr_orig```

- ```ln -s /opt/firefox/firefox/firefox /usr/lib/firefox-esr/firefox-esr```

- To update repeat wget and tar

## Bash Prompt

```
export PS1="\[\e[33m\]\u\[\e[m\]@\[\e[33m\]\h\[\e[m\] [\[\e[36m\]\w\[\e[m\]] [\[\e[35m\]\d\[\e[m\] \[\e[35m\]\@\[\e[m\]]\[\e[36m\]\\$\[\e[m\] "
```

## Enable Bitmap Fonts

- ```cd /etc/fonts/conf.d/```

- ```sudo rm -rf 70-no-bitmaps.conf && sudo ln -s ../conf.avail/70-yes-bitmaps.conf .```

- ```sudo dpkg-reconfigure fontconfig```

## Vim Airline plugin fonts fix

- ```git clone https://github.com/powerline/fonts.git```

    - ```cd fonts```

    - ```./install.sh```

## QEMU/KVM 20.04 Xorg crash leads to login loop

- ```sudo apt-get purge gstreamer1.0-vaapi```

- ```sudo apt-get autoremove --purge```

- Set virtio as GPU if not already selected (!)

- For vbox (!) use VMVGA

## QEMU/KVM Installation

- ```sudo apt-get install qemu qemu-kvm virt-manager```

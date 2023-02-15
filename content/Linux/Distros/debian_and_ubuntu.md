---
title: Debian (& PPAs)
author: csmertx
date: January 31, 2023
weight: -20
---

<br />

> PPAs and Debian are not always on speaking terms

> apti: sudo aptitude install

> aptr: sudo aptitude remove

## Adding Debian Backports Repo:
- ```sudov /etc/apt/sources.list```

    ```
    ++ deb http://deb.debian.org/debian buster-backports main contrib non-free
    ```

-To Use: ```apt-get -t buster-backports [install/remove] "package"```

## Adding Debian Testing repo:

- ```apti debian-keyring```

- ```apti debian-archive-keyring```

- ```vim /etc/apt/sources.list```

    ```
    ++ deb [trusted=yes] http://http.us.debian.org/debian/ testing non-free contrib main
    ```

- ```sudo apt-key adv --recv-keys --keyserver keyserver.ubuntu.com [key]```
- ```sudo apt-get update```

## Debian Backports

- Kernel/Headers

    - ```sudo apt-get -t buster-backports install linux-image-amd64 linux-headers-amd64```

- Mark as automatically installed for future sanity

    - ```apt-mark auto [manually-installed-backports-packages]```

## Debian and PPAs (not 100%)

- ```apti software-properties-common```

- ```sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys <previously unsigned key>```

## apt-get: Couldn't create temporary file

- ```sudo chown root:root /tmp (or /chroot/tmp)```

- ```sudo ugo+rwXt /tmp (...)```

## Theming

- ```apti gnome-shell-extensions```

- ```gtk3-engines-xfce```

## Pop OS

- ```sudo add-apt-repository ppa:system76/pop```

- ```sudo apt update```

- ```sudo apt install pop-theme pop-wallpapers```

## Development

```apti --install-suggests build-essential```

## Kubuntu manual updates (19.10)

```aptr plasma-discover```

> Should do it..

## Ubuntu manual Updates (19.10)
- ```sudov /etc/apt/apt.conf.d/20auto-upgrades```
    
    > change ```"1";``` to ```"0";```

    ```
    ++ APT::Periodic::Download-Upgradeable-Packages "0";
    ```
## Check <packagecandidate version before installing

```sudo apt-cache policy <package>```

## List all results from aptu (including not upgradable)

```apt-get update && apt-get -s upgrade```

## For an apt-get dummy run use:

```apt-get -s install <package>```

## Useful Packages

```build-essential```

## Changing hostname (because <sudo hostname newnamewould be too easy..)
```vi /etc/hostname```

```vi /etc/hosts```

```sudo service hostname start```

## Debian latest Firefox

- ```mkdir /opt/firefox```

- ```wget -O FirefoxSetup.tar.bz2   "https://download.mozilla.org/?product=firefox-latest&os=linux64&lang=en-US"```

- ```tar xjf FirefoxSetup.tar.bz2 -C /opt/firefox/```

- ```mv /usr/lib/firefox-esr/firefox-esr /usr/lib/firefox-esr/firefox-esr_orig```

- ```ln -s /opt/firefox/firefox/firefox /usr/lib/firefox-esr/firefox-esr```

- To update repeat ```wget``` and ```tar```

## Download Deb Packages to /home/$USER/tmp/dir

- ```mkdir /home/$USER/tmp```

- ```mkdir /home/$USER/tmp/archives```

- ```mkdir /home/$USER/tmp/archives/partial```

- note: if package is installed uninstall/download/reinstall

- ```apt-get install -d -o=dir::cache=/home/$USER/tmp/dir package```

## Enable bitmap fonts

- ```sudo rm -f /etc/fonts/conf.d/70-{yes,no,force}-bitmaps.conf```

```
if test -f /etc/fonts/conf.avail/70-force-bitmaps.conf; then
    sudo ln -s {../conf.avail,/etc/fonts/conf.d}/70-force-bitmaps.conf
else sudo ln -s {../conf.avail,/etc/fonts/conf.d}/70-yes-bitmaps.conf
fi
```

- ```sudo rm -rf /var/cache/fontconfig/*```

- ```rm -rf "$HOME/.fontconfig"```

- ```sudo fc-cache```

## Touchpad Tapping
- ```synclient TapButton3=2```

- ```synclient TapButton2=3```

- ```synclient TapButton1=1```

- or... create startup script containing these commands

    ```
    #!/bin/bash

    sudo xinput list
    sudo xinput list-props <number for touchpad/synaptic>
    sudo xinput set-prop <# for touchpad/synaptic> <# for Tapping Enabled> 1
    ```

## Printing
[Brother HL-2140 Driver Install Tool](https://support.brother.com/g/b/downloadend.aspx?c=us&lang=en&prod=hl2140_all&os=128&dlid=dlf006893_000&flang=4&type3=625)

> Enter hl2170w for device model (it just works)

## ZFS kmod (compiled)
- Dependencies

    - ```kmod-zfs```

    - ```zfs```

    - ```libzfs```

    - ```libzpool```

    - ```libuutil```

    - ```libnvpair```

    - ```zfs-dracut```

    - ```zfs-initramfs```

    - ```zfs-test```

## Slow Wifi

- ```sudov /etc/nsswitch.conf```

    ```
    -- hosts:		files mdns4_minimal [NOTFOUND=return] dns mdns4
    ++ hosts:		files dns
    ```

## Tear Free
- ```sudov /etc/X11/xorg.conf.d/20-radeon.conf```

    ```
    Section "Device"
            Identifier "Radeon"
            Driver "radeon"
            Option "TearFree" "on"
    EndSection
     ```

## Scripted Display Manager
- ```sudov /etc/X11/Xwrapper.config```

    ```
    -- allowed_users=console
    ++ allowed_users=anybody
    ++ needs_root_rights=yes
    ```

- ```sudov /etc/X11/xinit/xinitrc```
    -- . /etc/X11/Xsession
    ++ #. /etc/X11/Xsession
    ++ exec startkde

## Remove Libreoffice / firefox-esr

```
sudo apt-get/aptitude remove libreoffice-base libreoffice-common libreoffice-base-core libreoffice-core libreoffice-help-en-us firefox-esr
```

## Mirror Repositories (need a dedicated HDD/SSD)

- ```sudo apt-get install apt-mirror```

- ```sudov /etc/apt/mirror.list```

    - Select mirror

- ```sudo apt-mirror```

## Downloading other Architectures

- ```sudo --add-architecture armhf```

- ```sudo apt-get update```

- ```cd ~/.sources/armhf```

- ```sudo apt-cache search <package>```

- ```sudo apt-get download <package>:armhf```

## Youtube-dl

> Or the Youtube-dl fork [yt-dlp](https://github.com/yt-dlp/yt-dlp) with more features

- ```apti python3-pip```

- ```sudo pip3 install --upgrade youtube_dl```

## Unpack .deb containers

- ```apti binutils```

- ```cd /dir/withdeb```

- ```ar x [example.deb]```
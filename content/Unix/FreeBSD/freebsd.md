---
title: FreeBSD Installation
author: csmertx
date: February 7, 2023
weight: -20
---

> This page was created before 2022

> Please refer to the [FreeBSD Handbook](https://docs.freebsd.org/en/books/handbook/book/) for up to date installation instructions

## Live Login

- user: ```root```

- password: ```[automatic login]```

## First step

- Boot into the installed system before completing any of the following!

    > Full installation is covered via FreeBSD Handbook linked above

## Wifi troubles..

- ```vim /etc/rc.conf```

    ```
    -- ifconfig_em0="DHCP"
    -- ifconfig_em0_ipv6="inet6 accept_rtadv"
    ++ wlans_ath0="wlan0"
    ++ ifconfig_wlan0="WPA SYNCDHCP"
    ```


- ```ifconfig wlan0 create wlandev ath0```

- ```ifconfig wlan0 up scan```

- ```vim /etc/wpa_supplicant.conf```

    ```
    network={
        ssid="myssid"
        psk="mypsk"
    }
    ```

- ```service netif restart```

## Programs...

- If using ```zfs``` with < 8GB RAM perhaps install in chunks

### Setup for tiling window managers

> e.g. i3WM
```
pkg install p5-File-Locate vim neofetch py36-ranger w3m-img wget git firefox zsh bash compton redshift bspwm polybar unclutter nitrogen feh musicpd ncmpcpp mpv xorg xinput xf86-input-synaptics xf86-video-ati rxvt-unicode xarchiver thunar thunar-archive-plugin lxde-common lxde-icon-theme lxde-meta subversion gtk-arc-themes slim slim-freebsd-themes sudo htop dbus py27-glances vlc tmux fortune-mod-futurama cowsay sxiv xsel xdg-user-dirs alsa-utils pulseaudio hack-font
```

### Xfce desktop environment

- xfce-(current meta package--.e.g. xfce-4.12_1) thunar-(plugins--also don't forget to search for: freebsd | grep wallpapers) xfce(v)-power-manager alsa-utils pulseaudio xfce(v)-volumed-pulse xfce(v)-pulseaudio-plugin xfce(v)-notifyd xfce(v)-clipman-plugin plank

### Mate desktop environment

```
mate gnome3 vim sudo sxiv htop neofetch w3m py27-ranger cmake automake gcc wget git subversion papirus-icon-theme freebsd-8k-wallpapers firefox mpv vlc yank xsel xf86-input-synaptics xf86-video-ati xdg-user-dirs drm-kmod
```

## Create user dirs

- ```xdg-user-dirs-update```

## Optional Ports

- [FreeBSD / Docs: Chapter 4. Installing Applications: Packages and Ports](https://docs.freebsd.org/en/books/handbook/ports/#ports)

- [qutebrowser](https://cgit.freebsd.org/ports/tree/www/qutebrowser)

    > Keyboard driven open source web browser

## Touchpad

- [FreeBSD / Wiki / Synaptics Touchpad](https://wiki.freebsd.org/SynapticsTouchpad)

- ```sudov /boot/loader.conf```

    ```
    ++ hw.psm.synaptics_support="1"
    ```

- ```sudov /etc/sysctl.conf```

    ```
    ++ hw.psm.synaptics.vscroll_hor_area=1300
    ++ hw.psm.synaptics.min_pressure: 16
    ++ hw.psm.synaptics.max_pressure: 220
    ++ hw.psm.synaptics.max_width: 10
    ++ hw.psm.synaptics.weight_current: 3
    ++ hw.psm.synaptics.weight_previous: 6
    ++ hw.psm.synaptics.weight_previous_na: 20
    ++ hw.psm.synaptics.weight_len_squared: 2000
    ```

## ZFS Tuning (is fine)

- [FreeBSD / Wiki / ZFS Tuning GUide](https://wiki.freebsd.org/ZFSTuningGuide)

- ```sudov /boot/loader.conf```

    ```
    ++ vm.kmem_size="330M"
    ++ vm.kmem_size_max="330M"
    ++ vfs.zfs.arc_max="40M"
    ++ vfs.zfs.vdev.cache.size="5M"
    ```

## Radeon

> Solution screen tearing with older Radeon cards

> Defaults for Acer 5515 laptops

- ```vim /usr/local/etc/X11/xorg.conf.d/driver-radeon.conf```

    ```
    Section "Device"
        Identifier "Card0"
        Driver     "radeon"
        Option "TearFree" "on"
    EndSection
    ```

- ```vim /etc/rc.conf```

    ``` 
    ++ kld_list="radeonkms"
    ++ kld_list="/boot/modules/radeonkms.ko"    
    ```

- ```xorg -configure```

    > ```X -config /root/xorg.conf.new``` to check

- ```sudo pw usermod user -G video```

## locate

- ```/usr/libexec/locate.updatedb```

    > Stores file names in a globally accessible database

## UTF-8   Fonts

- [b1c1l1 blog - Using UTF-8 (Unicode) on FreeBSD](https://www.b1c1l1.com/blog/2011/05/09/using-utf-8-unicode-on-freebsd/)

- ```vim /etc/login.conf```

    ```
    --        :umask=022:
    ++        :umask=022:\
    ++        :charset=UTF-8:\
    ++        :lang=en_US.UTF-8:
    ```

- ```cap_mkdb /etc/login.conf```

- verify with ```locale```

- ```mkdir /usr/local/share/fonts/user```

- ```cd /usr/local/share/fonts/user```

- ```wget https://raw.githubusercontent.com/NerdyPepper/scientifica/master/regular/scientifica-11.```bdf

    > Scientifica Bitmap font

- ```wget https://raw.githubusercontent.com/csmertx/siji/master/bdf/siji.bdf```

    > Siji font for symbols and extended unicode characters

- ```vim /etc/X11/xorg.conf```

    > Just in case

    ```
    ++ Section "Files"
    ++    FontPath     "/usr/local/share/fonts/user"
    ++ EndSection
    ```

## Breeze/Snow Icons and Cursors

- ```cd /usr/local/share/icons```

- ```svn checkout https://github.com/KDE/breeze/trunk/cursors/Breeze_Snow```

- ```svn checkout https://github.com/KDE/breeze/trunk/cursors/Breeze```

- ```cp``` or ```move``` dir ```Breeze/cursors``` into ```/usr/local/share/icons/Breeze_```

- ```rm -rf``` dir ```Breeze```

- Rename ```Breeze_``` to ```Breeze```

## Papirus Desktop Icons

- [GitHub - PapirusDevelopmentTeam/papirus-icon-theme: Papirus icon theme for Linux](https://github.com/PapirusDevelopmentTeam/papirus-icon-theme)

```
wget -qO- https://raw.githubusercontent.com/PapirusDevelopmentTeam/papirus-icon-theme/master/install.sh | env DESTDIR="/usr/local/share/icons" sh
```

## Sudo

- ```vim /usr/local/etc/sudoers```

    ```
    -- # %wheel ALL=(ALL) ALL
    ++ %wheel ALL=(ALL) ALL
    ```

## User permissions for reboot, shutdown, halt

- [StackExchange: Poweroff or Reboot as normal User](https://unix.stackexchange.com/questions/85663/poweroff-or-reboot-as-normal-user#85665)

- ```vim /etc/defaults```

    ```
    ++ user ALL=(ALL) NOPASSWD: /sbin/reboot, /sbin/shutdown, /sbin/halt
    ```

    > Use sudo before executing reboot, shutdown, or halt

## rc.conf

> Enable system services including Slim display manager

- ```vim /etc/rc.conf```

    ```
    ++ ath_enable="YES"
    ++ dbus_enable="YES"
    ++ hald_enable="YES"
    ++ slim_enable="YES"
    ```

## Slim & Dual Monitor Setup

- ```ls /usr/local/share/slim/themes```

    > find a theme

- ```vim /usr/local/etc/slim.conf```

    > Edit theme

- ```vim ../themes/theme/slim.theme```

    > Change *_x values as needed (dual/multi monitor)

## startx

- ```vim ~/.xinitrc```

- ```exec startlxde 

    > Use LXDE.desktop as template for bspwm (or other tiling WMs like i3WM)

- ```cp /usr/local/share/xsessions/LXDE.desktop``` to ```/bspwm.desktop```

- ```vim /usr/local/share/xsessions/bspwm.desktop```

    ```
    -- Name=LXDE
    ++ Name=bspwm
    -- Exec=/usr/local/bin/lxde
    ++ Exec=/usr/local/bin/bspwm
    ```

- For ```GNOME``` try ```/usr/local/bin/gnome-session```

## Slim & Single Monitor

> Instructions specifically for use with [Ranger File Manager](/Linux/Software/ranger)

> ```sudo``` [PCManFM](https://www.freshports.org/x11-fm/pcmanfm/) for GUI

- ```sudo ranger /usr/local/share/slim/themes```

- ```yy``` copy dir ```/usr/local/share/slim/themes/default```

- ```pp``` paste dir ```/usr/local/share/slim/themes/default_```

- ```dD``` trash ```/usr/local/share/slim/themes/default/*```

- ```yy``` copy ```/usr/local/share/slim/themes/freebsd-simple/*```

- ```pp``` paste ```/usr/local/share/slim/themes/freebsd-simple```

- ```cw``` rename ```freebsd-simple``` to ```default```

## xfce4-terminal

- ```hack 9``` font

- Terminal size: ```85x29```

- See [Xresources](/Linux/Assorted/xresources) for ```URxvt```, ```xterm``` or other terminal emulators

## zsh

- ```chsh -s /usr/local/bin/zsh $USER```

## Nextcloud

- Download the tar file from the local cloud to complete the setup

    > I'm going to leave this here, but I think this was specific to a machine I used in 2018

## Kernel Panic

- Escape to loader prompt

    > Don't Panic

- ```show```

    > Refresher of ```/boot/loader.conf``` & ```/boot/device.hints```

- ```set``` that one ```random.optionfrom.internet.0.disable=0```

- And you'll be saved

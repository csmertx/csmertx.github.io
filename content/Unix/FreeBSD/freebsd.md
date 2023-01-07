---
title: FreeBSD > Installation
weight: -20
---

## FreeBSD Installation Notes

### Live Login
- user: root
- password: {automatic login}

### Take note
=> boot into the system before completing any of the following!

### Wifi troubles..
=> vim /etc/rc.conf (sometimes...)
```
-- ifconfig_em0="DHCP"
-- ifconfig_em0_ipv6="inet6 accept_rtadv"
++ wlans_ath0="wlan0"
++ ifconfig_wlan0="WPA SYNCDHCP"
```

=> ifconfig wlan0 create wlandev ath0 (sometimes..)
=> ifconfig wlan0 up scan (bork or no bork?..)
=> vim /etc/wpa_supplicant.conf
```
network={
    ssid="myssid"
    psk="mypsk"
}
```
=> service netif restart

### Programs...
=> if zfs and low RAM perhaps install in chunks
=> pkg install p5-File-Locate vim neofetch py36-ranger w3m-img wget git firefox zsh bash compton redshift bspwm polybar unclutter nitrogen feh musicpd ncmpcpp mpv xorg xinput xf86-input-synaptics xf86-video-ati rxvt-unicode xarchiver thunar thunar-archive-plugin lxde-common lxde-icon-theme lxde-meta subversion gtk-arc-themes slim slim-freebsd-themes sudo htop dbus py27-glances vlc tmux fortune-mod-futurama cowsay sxiv xsel xdg-user-dirs alsa-utils pulseaudio hack-font
for XFCE...
=> xfce-(current meta package--.e.g. xfce-4.12_1) thunar-(plugins--also don't forget to search for: freebsd | grep wallpapers) xfce(v)-power-manager alsa-utils pulseaudio xfce(v)-volumed-pulse xfce(v)-pulseaudio-plugin xfce(v)-notifyd xfce(v)-clipman-plugin plank
=> mate gnome3 vim sudo sxiv htop neofetch w3m py27-ranger cmake automake gcc wget git subversion papirus-icon-theme freebsd-8k-wallpapers firefox mpv vlc yank xsel xf86-input-synaptics xf86-video-ati xdg-user-dirs drm-kmod

### Create user dirs
=> xdg-user-dirs-update

### Optional Ports
=> qutebrowser

### Touchpad
=> https://wiki.freebsd.org/SynapticsTouchpad
=> sudov /boot/loader.conf
```
++ hw.psm.synaptics_support="1"
```
=> sudov /etc/sysctl.conf
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

### ZFS Tuning (is fine)
=> https://wiki.freebsd.org/ZFSTuningGuide
=> sudov /boot/loader.conf
```
++ vm.kmem_size="330M"
++ vm.kmem_size_max="330M"
++ vfs.zfs.arc_max="40M"
++ vfs.zfs.vdev.cache.size="5M"
```

### Radeon (5515 just defaults...)
=> vim /usr/local/etc/X11/xorg.conf.d/driver-radeon.conf
```
Section "Device"
    Identifier "Card0"
    Driver     "radeon"
    Option "TearFree" "on"
EndSection
```

=> vim /etc/rc.conf
```
++ kld_list="radeonkms" (probably not for the 5515..)
++ kld_list="/boot/modules/radeonkms.ko"
```
=> xorg -configure (X -config /root/xorg.conf.new to check)
=> sudo pw usermod chris -G video

### locate
=> /usr/libexec/locate.updatedb (bad practice for true multi user installations)

### UTF-8   Fonts
=> https://www.b1c1l1.com/blog/2011/05/09/using-utf-8-unicode-on-freebsd/
=> vim /etc/login.conf
```
--        :umask=022:
++        :umask=022:\
++        :charset=UTF-8:\
++        :lang=en_US.UTF-8:
```

=> cap_mkdb /etc/login.conf
=> verify with command locale
=> mkdir /usr/local/share/fonts/user
=> cd /usr/local/share/fonts/user
=> wget https://raw.githubusercontent.com/NerdyPepper/scientifica/master/regular/scientifica-11.bdf
=> wget https://raw.githubusercontent.com/csmertx/siji/master/bdf/siji.bdf
=> vim /etc/X11/xorg.conf (probably not necessary)
```
++ Section "Files"
++    FontPath     "/usr/local/share/fonts/user"
++ EndSection
```

### Breeze/Snow
=> cd /usr/local/share/icons
=> svn checkout https://github.com/KDE/breeze/trunk/cursors/Breeze_Snow
=> svn checkout https://github.com/KDE/breeze/trunk/cursors/Breeze
=> sudor /usr/local/share/icons
=> pull Breeze/cursors out into /usr/local/share/icons/Breeze_
=> dD Breeze
=> cw rename Breeze_ to Breeze

### Papirus Desktop Icons
=> https://github.com/PapirusDevelopmentTeam/papirus-icon-theme
=> wget -qO- https://raw.githubusercontent.com/PapirusDevelopmentTeam/papirus-icon-theme/master/install.sh | env DESTDIR="/usr/local/share/icons" sh

### Sudo
=> vim /usr/local/etc/sudoers
```
-- # %wheel ALL=(ALL) ALL
++ %wheel ALL=(ALL) ALL
```

=> https://unix.stackexchange.com/questions/85663/poweroff-or-reboot-as-normal-user#85665

### User permissions for reboot, shutdown, halt
=> vim /etc/defaults
```
++ chris ALL=(ALL) NOPASSWD: /sbin/reboot, /sbin/shutdown, /sbin/halt
```
(use sudo before executing reboot, shutdown, or halt)

## rc.conf
=> vim /etc/rc.conf
```
++ ath_enable="YES"
++ dbus_enable="YES"
++ hald_enable="YES"
++ slim_enable="YES"
```

### Slim & Dual Monitor Setup
=> ls /usr/local/share/slim/themes (find a theme)
=> vim /usr/local/etc/slim.conf (edit theme)
=> vim ../themes/theme/slim.theme
=> Change *_x values as needed (dual/multi monitor)

### startx
=> vim ~/.xinitrc
=> exec startlxde (jumpoff for bspwm)
=> cp /usr/local/share/xsessions/LXDE.desktop to "/bspwm.desktop
=> vim /usr/local/share/xsessions/bspwm.desktop
```
-- Name=LXDE
++ Name=bspwm
-- Exec=/usr/local/bin/lxde
++ Exec=/usr/local/bin/bspwm
```
=> gnome is /usr/local/bin/gnome-session

### Slim & Single Monitor
=> ranger /usr/local/share/slim/themes
=> yy /usr/local/share/slim/themes/default
=> pp /usr/local/share/slim/themes/default_
=> dD /usr/local/share/slim/themes/default/*
=> yy /usr/local/share/slim/themes/freebsd-simple/*
=> pp /usr/local/share/slim/themes/freebsd-simple
=> cw rename freebsd-simple to default

### xfce4-terminal
=> hack 9 font
=> 85x29

### zsh
=> chsh -s /usr/local/bin/zsh $USER

### nextcloud
=> download the tar file from the local cloud to complete the setup

### Kernel Panic
=> Escape to loader prompt
=> show (refresher of /boot/loader.conf & /boot/device.hints)
=> set <random.optionfrom.internet.0.disable=0>

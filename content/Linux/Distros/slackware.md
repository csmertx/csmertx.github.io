---
title: Slackware
author: csmertx
date: February 1, 2023
weight: -20
---

> Slackware as a virtualized system and beyond

> I believe these notes are for Slackware Current (it was before 2022)

## Installation

- Lilo & Virtio

    - Exit installer > Don't reboot..

    - ```cfdisk /dev/vda``` 
    
        > Set bootable > write > exit

    - ```chroot /mnt```

    - ```ls /boot``` 
    
        > $KERNEL version here

    - ```/usr/share/mkinitrd/mkinitrd_command_generator.sh``` 
    
        > Might help..

    - ```mkinitrd -c -k 4.4.14 -f ext4 -m ext4:virtio:virtio_balloon:virtio_blk:virtio_pci:virtio_ring```

    - ```ln -s /boot/vmlinuz-generic-4.4.14 /boot/vmlinuz```

        - or

        - ```ln -s /boot/vmlinuz-huge-4.4.14 /boot/vmlinuz```

    - ```vim /etc/lilo.conf```

         ```
         boot=/dev/vda
         disk=/dev/vda bio=0x80 max-partitions=7
         #scrolldown# after # Linux bootable
         image = /boot/vmlinuz2
         initrd = /boot/initrd.gz
         root = /dev/vda1
         label = Linux2
         read-only
         ```

    - ```exit```
        
        > Leave chroot

    - ```lilo -C /mnt/etc/lilo.conf```

## Swap Lilo for Grub2

- pkgtool > remove packages > lilo

- ```dhcpcd```

- ```chroot /mnt```

- ```vi /etc/resolv.conf```

    ```
    ++ nameserver 8.8.8.8
    ```

- ```grub-install --target=i386-pc /dev/sdX```

- ```grub-mkconfig -o /boot/grub/grub.cfg``` 

    > Upgrades too

## Create User

- ```useradd -m -G wheel,video,audio -s user```

## UPDATE!

- ```sudov /etc/slackpkg/blacklist```

    ```
    ++ kernel-generic
    ++ kernel-generic-smp
    ++ kernel-huge
    ++ kernel-huge-smp
    ++ kernel-modules
    ++ kernel-modules-smp
    ```

- ```sudov /etc/slackpkg/mirrors```

    - Uncomment: http://slackbuilds.org...

        > 02-02-2023: I can't remember why I wrote this...

- ```slackpkg update```

- ```slackpkg upgrade slackpkg```

- ```slackpkg new-config```

- ```slackpkg upgrade glibc-solibs```

    > After new releases

- ```slackpkg install-new```

- ```slackpkg upgrade-all```

- ```slackpkg clean-system```

- ```/usr/share/mkinitrd/mkinitrd_command_generator.sh -k newkernel```

    > ```ls /boot``` to grep newkernel name

## Configuration

- Virtual machine: QXL 16M

- ```echo "source ~/.bashrc" >> ~/.bash_profile```

- ```vim ~/.bashrc```

    ```
    shopt -s histappend
    HISTSIZE=20000
    HISTFILESIZE=20000
    shopt -s checkwinsize
    export PS1='\n\u@\h - [\w]\n$ '
    alias qq='exit'
    alias cls='clear'
    alias ll='ls -la'
    alias ra='ranger'
    alias sudoc='sudo chmod +x'
    alias sudor='sudo ranger'
    alias sudov='sudo vim'
    ```

- ```xdg-user-dirs-update```

    > Generate desktop /home/user/.. folder stuff

- ```xorgsetup```

- ```xwmconfig```

    > Not a DM config but still..

## Network while Chroot(ing)

- ```sudo vim /etc/resolv.conf```

    ```
    ++ nameserver 8.8.8.8
    ```

## Sbopkg Setup + Options

- Slackbuilds.org package browser
 
    - [Download](https://sbopkg.org/downloads.php) Sbopkg Slackbuild

- ```wget sbopkg-x.xx.x-noarch_1_wzr.tgz```

- ```installpkg sbopkg-x.xx.x-noarch_1_wzr.tgz```

- ```sbopkg -r package```

    > Sync repos

- ```sbopkg -s package```

    > Search by ```package```

- sbopkg -b package

    > List details of ```package```

- ```sbopkg -i package``` 

    > Install ```package```

- ```sbopkg remove package```

    > Remove ```package```

- ```sbopkg -u```

    > Update ```sbopkg```

- ```sbopkg -c```
    
    > List installed packages and show updates

- ```sbopkg -P```

    > List package cache and purge unneeded packages

- ```sbopkg -p```

    > List installed packages

## Sbopkg Examples

- ```sbopkg -r```

    > Wait like 10min+

- ```sbopkg -s '(asterisk)[Ww]allpapers(asterisk)'```

- ```sbopkg -i slack-wallpapers```

## slackbuilds.org/repository

- ```echo "export TMP="$HOME/.sources/SBo"" >> $HOME/.bashrc```

- ```cd $HOME/.sources/slackbuilds```

- ```wget www.slackbuilds....tar.gz```

    > Slackbuild search linked [Below](#resources)

- ```tar -xzf slackbuild.tar.gz```

- ```cd packagedir```

- ```wget www.source.tar.gz```

- ```sudoc package.SlackBuild```

- ```./package.Slackbuild```

- ```cd ../SBo```

- ```installpkg ...SBo.tgz```

- ```removepkg ...SBo.tgz```

- ```upgradepkg ...SBo.tgz```

## Xorg

- ```sudo xorgsetup```

- Change vesa to qxl

- Install ```xf86-video-qxl```

    > Slackbuild search linked [Below](#resources)

- ```sudo netconfig```

    > Networkmanager dependencies satisfied

- See [XrandR](/Linux/Assorted/xrandr) to set display resolutions 1600x900 and beyond, etc.

## Display Manager (KDM/KDE & xrandr (!))

- ```sudov /etc/inittab```

    ```
    -- id:3:initdefault:
    ++ id:4:initdefault:
    ```

## UTF-8

- ```sudo cp /usr/share/zoneinfo/America/Anchorage /etc/localtime```

    > 02-02-2023: Instead of New York? I can't remember why..

- ```sudov /etc/profile.d/lang.sh```

- ```sudo /etc/profile.d/lang.sh```

## Modernize Ruby

- ```sudo slackpkg remove ruby```

- ```wget https://cache.ruby-lang.org/pub/ruby/2.7/ruby-2.7.0.tar.gz```

    > ```ruby-x.x.x.tar.gz```

- ```tar -xzf ruby-2.7.0.tar.gz```

    > ```ruby-x.x.x.tar.gz```

- ```cd ruby-2.7.0```

    - ```./configure```

    - ```make```

    - ```make install```

- ```sudo ln -sf /usr/local/bin/gem /usr/bin/gem```

## Flatpak

> Chain of dependencies to 

- Requires:

    - [bubblewrap](https://slackbuilds.org/repository/15.0/system/bubblewrap/?search=bubblewrap) [ostree](https://slackbuilds.org/repository/15.0/system/ostree/?search=ostree) [appstream-glib](https://slackbuilds.org/repository/15.0/libraries/appstream-glib/?search=appstream-glib) [libseccomp](https://www.slackware.nl/slackware/slackware-current/source/l/libseccomp/) [xdg-desktop-portal-gtk](https://slackbuilds.org/repository/15.0/desktop/xdg-desktop-portal-gtk/?search=xdg-desktop-portal-gtk)

        - [appstream-glib](https://slackbuilds.org/repository/15.0/libraries/appstream-glib/?search=appstream-glib)

            - [gcab](https://slackbuilds.org/repository/15.0/libraries/gcab/?search=gcab)

                - [vala](https://slackbuilds.org/repository/15.0/development/vala-12/)

            - [meson](https://mirrors.slackware.com/slackware/slackware/source/d/meson/)

                - [python3](https://mirrors.slackware.com/slackware/slackware-current/source/d/python3/)

                - [ninja](https://slackware.pkgs.org/current/slackware-x86_64/ninja-1.11.1-x86_64-1.txz.html)

        - xdg-desktop-portal-gtk

            > Linked above

            - xdg-desktop-portal

                > Same package as ```xdg-desktop-portal-gtk```

                - [json-glib](https://slackware.pkgs.org/14.2/cinnamon-x86_64/json-glib-1.2.8-x86_64-1_csb.txz.html)

                - [pipewire](https://slackware.pkgs.org/current/alienbob-x86_64/pipewire-jack-0.3.63-x86_64-1alien.txz.html)

                    - meson

                        > Linked above

- Add Flathub

    - ```flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo```

- ```groupadd flatpak```

- org.freedesktop.Platform.openh264 fails...

    > This happens even with Ubuntu or Arch Linux systems

    - ```flatpak install flathub org.freedesktop.Platform```

- Ready for: ```flatpak install flathub xxx.oranization.[Pp]ackage```

    > Not a guarantee, but the potential to run the latest software is there

## Resources

- [Slackware Homepage](https://slackware.nl)

- [Slackware Linux Essentials: Handbook](https://www.slackbook.org/html/book.html)

- [Slackware Builds: Search](http://slackbuilds.org)

- [PKG.org: Slackware Repositories](https://slackware.pkgs.org)
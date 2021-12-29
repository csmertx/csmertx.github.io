### Installation
- Lilo & Virtio (IDE probably fine here..)
    - Exit installer > Don't reboot..
    - cfdisk /dev/vda # Set bootable > write > exit
    - chroot /mnt
    - ls /boot #$KERNEL version here
    - /usr/share/mkinitrd/mkinitrd_command_generator.sh #Might help..
    - mkinitrd -c -k 4.4.14 -f ext4 -m ext4:virtio:virtio_balloon:virtio_blk:virtio_pci:virtio_ring
    - 1: ln -s /boot/vmlinuz-generic-4.4.14 /boot/vmlinuz
    - or
    - 2: ln -s /boot/vmlinuz-huge-4.4.14 /boot/vmlinuz
    - vim /etc/lilo.conf
    - boot=/dev/vda
    - disk=/dev/vda bio=0x80 max-partitions=7
    - #scrolldown# after # Linux bootable
    - image = /boot/vmlinuz2
    - initrd = /boot/initrd.gz
    - root = /dev/vda1
    - label = Linux2
    - read-only
    - exit #leave chroot
    - lilo -C /mnt/etc/lilo.conf

### Swap Lilo for Grub2
- pkgtool > remove packages > lilo
- dhcpcd
- chroot /mnt
- /etc/resolv.conf
- nameserver 8.8.8.8
- grub-install \--target=i386-pc /dev/sdX
- grub-mkconfig -o /boot/grub/grub.cfg #Upgrades too

### Create User
- useradd -m -G wheel,video,audio -s chris

### UPDATE!
- sudov /etc/slackpkg/blacklist
    - ++ kernel-generic
    - ++ kernel-generic-smp
    - ++ kernel-huge
    - ++ kernel-huge-smp
    - ++ kernel-modules
    - ++ kernel-modules-smp
- sudov /etc/slackpkg/mirrors
- Uncomment: http://slackbuilds.org...
- slackpkg update
- slackpkg upgrade slackpkg
- slackpkg new-config
- slackpkg upgrade glibc-solibs # After new releases
- slackpkg install-new
- slackpkg upgrade-all
- slackpkg clean-system
- /usr/share/mkinitrd/mkinitrd_command_generator.sh -k newkernel #ls /boot

### Configuration
- QXL 16M
- echo "source ~/.bashrc" >> ~/.bash_profile
- vim ~/.bashrc
    - shopt -s histappend
    - HISTSIZE=20000
    - HISTFILESIZE=20000
    - shopt -s checkwinsize
    - export PS1='\n\u@\h - [\w]\n$ '
    - alias qq='exit'
    - alias cls='clear'
    - alias ll='ls -la'
    - alias ra='ranger'
    - alias sudoc='sudo chmod +x'
    - alias sudor='sudo ranger'
    - alias sudov='sudo vim'
- xdg-user-dirs-update # Generate niffy home folders
- xorgsetup
- xwmconfig (not a DM config but still..)

### Resources
- lynx https://www.slackbook.org/html/book.html

### Network while Chroot(ing)
- sudo vim /etc/resolv.conf
- ++ nameserver 8.8.8.8

### Sbopkg Setup + Options
- https://sbopkg.org/downloads.php
- wget sbopkg-x.xx.x-noarch\_1\_wzr.tgz
- installpkg sbopkg-x.xx.x-noarch\_1\_wzr.tgz
- sbopkg -r package (sync repos)
- sbopkg -s package (search)
- sbopkg -b package (details)
- sbopkg -i package (install)
- sbopkg remove package
- sbopkg -u (update sbopkg)
- sbopkg -c (list installed packages, show updates)
- sbopkg -P (list package cache--purge unneeded)
- sbopkg -p (list installed packages)

### Sbopkg Example
- sbopkg -r (wait like 10min+)
- sbopkg -s '(asterisk)[Ww]allpapers(asterisk)'
- sbopkg -i slack-wallpapers

### slackbuilds.org/repository
- echo "export TMP="$HOME/.sources/SBo"" >> $HOME/.bashrc
- cd $HOME/.sources/slackbuilds
- wget www.slackbuilds....tar.gz
- tar -xzf slackbuild.tar.gz
- cd packagedir
- wget www.source.tar.gz
- sudoc package.SlackBuild
- ./package.Slackbuild
- cd ../SBo
- installpkg ...SBo.tgz
- removepkg ...SBo.tgz
- upgradepkg ...SBo.tgz

### Xorg
- sudo xorgsetup
- Change vesa to qxl
- xf86-video-qxl (slackbuilds)
- sudo netconfig (makes networkmanager very happy)
- see xrandr.md to set 1600x900, etc.

### Display Manager (KDM/KDE & xrandr (!))
- sudov /etc/inittab
- \-- id:3:initdefault:
- ++ id:4:initdefault:

### UTF-8
- sudo cp /usr/share/zoneinfo/America/Anchorage /etc/localtime (because reasons)
- sudov /etc/profile.d/lang.sh
- sudo /etc/profile.d/lang.sh

### Modernize Ruby
- sudo slackpkg remove ruby
- wget https://cache.ruby-lang.org/pub/ruby/2.7/ruby-2.7.0.tar.gz (x.x.x)
- tar -xzf ruby-2.7.0.tar.gz (x.x.x)
- cd ruby-2.7.0
- ./configure
- make
- make install
- sudo ln -sf /usr/local/bin/gem /usr/bin/gem

### Flatpak
- Requires:
    - (todo: sort) bubblewrap ostree appstream-glib libseccomp xdg-desktop-portal-gtk
        - appstream-glib
            - gcab
                - vala
            - meson
                - python3
                - ninja
        - xdg-desktop-portal-gtk
                - xdg-desktop-portal
                    - json-glib
                    - pipewire
                        - meson
- Add Flathub
    - flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
- groupadd flatpak
- org.freedesktop.Platform.openh264 fails...
    - flatpak install flathub org.freedesktop.Platform
- flatpak install flathub xxx.oranization.[Pp]ackage

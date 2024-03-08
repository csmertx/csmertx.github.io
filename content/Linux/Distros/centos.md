---
title: 💻 CentOS 8 Stable
author: csmertx
date: January 31, 2023
weight: -20
---

<br />

## Instructions for Virtualized CentOS

> This information is obviously out of date as of 2022

> Automation to spin up 5 VMs in a cluster I called the [Vorta](https://memory-alpha.fandom.com/wiki/Category:Vorta) cluster.. because each of the 4 nodes was named [Weyoun](https://memory-alpha.fandom.com/wiki/Weyoun)

- Default Desktop

    - 768M RAM

    - 8-15G Storage Space

    - ```sudo dnf remove firefox```

    - ```sudo dnf update``` 
    
        > Necessary

    - ```sudo dnf install tar bzip2 kernel-devel-$(uname -r) kernel-headers perl gcc make elfutils-libelf-devel```

    - Insert Guest Additions & Cancel Auto Install

    - ```cd /run/medai/$USER/VBox_GAs_x.x.x```

    - ```sudo ./VBoxLinuxAdditions.run```

    - Wired Connection (top right) > Wired Settings > Wired (Gear Icon) > Connect Automatically

    - Reboot

- Headless Node

    - Installation

        - DVD Media

        - 128M Video

        - 1024G RAM

        - 12G Storage

        - Software Selection > Server

        - Network & Host Name > Network On > hostname: weyoun@c8n1 (centos version/node number)

        - Create User > Weyoun > Advanced > wheel, sudo

    - Weyoun Cluster

        - virt-manager

            - vorta@c8n0  - http://192.168.100.162

            - weyoun@c8n1 - http://192.168.100.173

            - weyoun@c8n2 - http://192.168.100.185

            - weyoun@c8n3 - http://192.168.100.181

            - weyoun@c8n4 - http://192.168.100.252

        - Check with router home page..

        - VBox

            - weyoun@c8n0 - http://192.168.254.69

            - weyoun@c8n1 - http://192.168.254.74

            - weyoun@c8n2 - http://192.168.254.81

            - weyoun@c8n3 - http://192.168.254.78

            - weyoun@c8n4 - http://192.168.254.79

## General System Stuff

- ```sudo dnf update```

### Changing hostname

- ```sudo hostnamectl set-hostname your-new-hostname```

- ```sudo systemctl restart systemd-hostnamed```

### Network Configuration

- ```sudo nmtui-edit```

- ```sudo nmtui-connect```

- ```sudo yum groupinstall 'Development Tools'```

- ```sudo dnf install epel-release```

    > Fedora Epel Repository

- ```sudo dnf config-manager --set-enabled PowerTools```

- ```sudo dnf install htop tmux neofetch git gtk2-devel gnome-tweaks dconf-editor cmake```

- ```sudo dnf install python3-pip```

    > Might already be installed

- ```sudo pip3 install ranger-fm docutils```

- ```sudo dnf install ruby rxvt-unicode libcurl-devel nmap sshpass libXt-devel```

- ```sudo gem install tmuxinator```

### Enable bitmap fonts

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

- ```fc-cache```

### Center Windows

- ```dconf-editor``` find ```/org/gnome/mutter/```, and check ```center-new-windows```

### yank

- ```cd ~/.sources && git clone https://github.com/mptre/yank.git```

- ```sudo make install```

### xsel

- ```curl -OL http://www.vergenet.net/~conrad/software/xsel/download/xsel-1.2.0.tar.gz```

- ```tar -xzf xsel-1.2.0.tar.gz```

- ```cd xsel-1.2.0```

- ```./configure```

- ```vim Makefile```

- Jump to line 98

    > Vim: ```:98```

- Jump to end of line

    > Vim: ```SHIFT``` + ```A```

- ```-Wno-error=stringop-truncation```

    > Resolves conflict with new GCC)

- ```make```

- ```make check```

- ```sudo make install```

### Hack font

- https://github.com/source-foundry/Hack/releases (tarball)

- ```tar -xzf hack.tar.gz```

- ```mkdir ~/.local/share/fonts && cp -f ttf ~/.local/share/fonts/ttf```

- ```fc-cache -f -v```

### xarchiver

- ```wget https://sourceforge.net/projects/xarchiver/files/xarchiver-0.5.4.tar.bz2```

- ```./configure```

- ```sudo make install```

### dwm

- ```git clone git://git.suckless.org/dwm```

- ```cd dwm```

- ```vim config.def.h```

    ```
    -- static const char *termcmd[] = { "st", NULL };
    ++ static const char *termcmd[] = { "gnome-terminal", NULL };
    ```

- ```sudo make clean install```

- ```cp /usr/share/xsessions /usr/share/xsessions```

    - change stuff for dwm (```exec /usr/local/bin/dwm```, etc.)

- dmenu

    - ```git clone git://git.suckless.org/dmenu```

    - ```cd dmenu```

    - ```sudo make clean install```

### lxappearance

- ```wget https://downloads.sourceforge.net/lxde/lxappearance-0.6.3.tar.xz```

- ```tar -xf lxappearance-0.6.3.tar.xz```

- ```cd lxappearance-0.6.3.tar.xz```

- ```./configure```

- ```sudo make install```

### feh image viewer

- ```wget http://feh.finalrewind.org/feh-3.3.tar.bz2```

- requires: ```libpng``` & ```imlib2```

    - ```wget https://downloads.sourceforge.net/enlightenment/imlib2-1.6.1.tar.bz2```

    - ```tar -xf imlib2-1.6.1.tar.bz2```

    - ```cd imlib2-1.6.1```

    - ```./configure```

    - ```sudo make install```

- ```tar -xf feh-3.3.tar.bz2```

- ```cd feh-3.3```

- ```make; sudo make install```

- ```mkdir ~/Pictures/backgrounds```

- ```cd ~/.Pictures/backgrounds```

- ```wget https://images.alphacoders.com/789/789948.jpg```

- Add ```feh --bg-scale ~/Pictures/backgrounds/789948.jpg``` to ```~/.xinitrc```

### arandr

- ```git clone https://gitlab.com/arandr/arandr```

- ```cd arandr```

- ```sudo ./setup.py install```

- Reset resolution + save

- Add ```~/.screenlayout/script.sh``` to ```~/.xinitrc``` before all GUI stuff
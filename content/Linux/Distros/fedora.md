---
title: Fedora
author: csmertx
date: February 1, 2023
weight: -20
---

# Fedora additional package sources and other tweaks

## RPM Fusion

```
sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```

### RPMSphere (gufw)
```rpm -Uvh 'https://github.com/rpmsphere/noarch/blob/master/r/rpmsphere-release-30-1.noarch.rpm?raw=true'```

### Fedora as QEMU Guest

- Copy Paste between guest/host and more (auto install with desktops)

    - ```sudo dnf install spice-vdagent```
        
        > Spice

    - ```sudo dnf install qemu-guest-agent```
    
        > QEMU

- QXL Video Driver (great w/XFCE)

    - ```sudo dnf install xorg-x11-drv-qxl```
    
        > Auto installed with desktops?

- Virtio/OpenGL might be best for KDE/Plasma

## Development Packages

```sudo yum groupinstall "Development Tools" "Development Libraries"```

## Hack Font

- ```wget https://github.com/source-foundry/Hack/releases/download/v3.003/Hack-v3.003-ttf.zip```

- ```mv Hack-v... ~/.local/share/fonts/Hack-v...```

- ```unzip Hack-v...```

## Update Grub

- ```grub2-mkconfig -o /boot/grub2/grub.cfg```

### Tilda

- As of Fedora 32 (or 200318)..

- [lanoxx/Tilda](https://github.com/lanoxx/tilda)

## Autostart

- ```mkdir ~/.config/autostart```

- ```for file in /usr/share/applications/{guake,clipit,stardict}.desktop; do cp $file ~/.config/autostart; done```

## Hotkeys (!)(x)

- ```ALT + F2``` ```dconf-editor```

- org > gnome > mutter > wayland > xwayland-grab-access-rules

- Uncheck: Use default value

    ```
    Custom value: ['clipit,stardict,guake,firefox,gnome-boxes,remote-viewer,virt-viewer,virt-manager,vncviewer,Xephyr,vinagre,mpv,xmodmap']
    ```

- Plus future apps as well

### Resources

- [RPM Find](https://rpmfind.net)
    
    > duckduckgo.com [bang](https://duckduckgo.com/bangs): ```!rpm [package-name]```

- [Fedora Project Packages](https://apps.fedoraproject.org/packages)

    > duckduckgo.com [bang](https://duckduckgo.com/bangs): ```!fedorapkg [package-name]```

- [Fedora Wiki](https://fedoraproject.org/wiki) 

    > duckduckgo.com [bang](https://duckduckgo.com/bangs): ```!fedorawiki [search-terms]```

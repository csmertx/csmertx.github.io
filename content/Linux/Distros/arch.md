## Arch Linux Installation and Maint. notes

### Verify ISO
- gpg \--keyserver pgp.mit.edu \--keyserver-options auto-key-retrieve \--verify   archlinux-xxxx.xx.xx-x86_64.iso.sig archlinux-xxxx.xx.xx-x86_64.iso
- md5sum archlinux-xxxx.xx.xx-x86_64.iso

### Wifi
- cp /etc/netctl/examples/wireless-wpa /etc/netctl/<essid name>
- Edit /etc/netctl/<essid name> to change: Interface (ip link), ESSID, and Key
- netctl start <essid name>

### Chroot to save the system
- mount /dev/sd<Arch> /mnt
- mount /dev/sd<Grub> /mnt/boot
- cd /mnt
- mount -t proc proc /mnt/proc
- mount -t sysfs sys /mnt/sys
- mount -o bind /dev /mnt/dev
- mount -t devpts pts /mnt/dev/pts
- chroot /mnt
- pac -Syu == failed retrieving file ..
    - sudov /etc/resolv.conf
        - Add: nameserver 8.8.8.8

### Create Partition(s)
- fdisk /dev/sdXX (fdisk -l)
- n (new)
- w (write)

### Format ext4
- mkfs.ext4 -O "^has_journal" /dev/sdXX (no journal)
- mkfs.ext4 /dev/sdXX

### Disable KMS if needed
- vi /boot/grub/grub.conf
```
++ append "nomodeset" to kernel line
```

### Send systemd journal writes to RAM
- mkdir /etc/systemd/journald.conf.d
- vi /etc/systemd/journald.conf.d/usbstick.conf
```
++ [Journal]
++ Storage=volatile
++ RunTimeMaxUse=30M
```

### Limit System calls and unnecessary program writes
- pac -S libeatmydata
- append "eatmydata" before calling a program
- .e.g. vi ~/.config/i3/config
```
++ exec \--no-startup-id eatmydata firefox
```

### Mount disk to /mnt
- mount /dev/sXX /mnt

### Base system
- pacstrap /mnt base linux linux-headers linux-firmware bash man-db man-pages texinfo wireless_tools wpa_supplicant wireless-regdb sudo ntfs-3g e2fsprogs dhcpcd grub vim netctl which xorg-xinit xorg-twm xterm git fakeroot binutils make gcc network-manger network-manager-applet

### Fstab
- genfstab -U /mnt >> /mnt/etc/fstab

### Chroot
- arch-chroot /mnt

### Mirror List
- vim /etc/pacman.d/mirrorlist

### Time Zone
- mkdir /etc/localtime (probably needed)
- ls -sf /usr/share/zoneinfo/America/New_York /etc/localtime
- hwclock \--systohc

### Localization (Unicode)
- sudov /etc/locale.gen
- \-- #en_US.UTF-8 UTF-8
- ++ en_US.UTF-8 UTF-8
- locale-gen
- vim /etc/locale.conf
- ++ LANG=en_US.UTF-8

### Network Configuration
- vim /etc/hostname
- ++ __myhostname
- vim /etc/hosts
- ++ 127.0.0.1     localhost
- ++ ::1           localhost
- ++ 127.0.1.1     myhostname.localdomain  myhostname

### Initramfs
- mkinitcpio -P

### Root Password
- passwd

### Grub
- grub-install \--target=i386-pc /dev/sdX
- grub-mkconfig -o /boot/grub/grub.cfg

### Reboot & Ethernet
- systemctl enable dhcpcd
- systemctl start dhcpcd
- exit
- umount /mnt
- reboot

### Post installation Packages
- pacman -S base base-devel linux linux-headers linux-firmware bash man-db man-pages texinfo wireless_tools wpa_supplicant wireless-regdb sudo ntfs-3g e2fsprogs (if not with pacstrap)

- pacman -S archlinux-keyring networkmanager network-manager-applet gvim xorg xorg-apps xf86-video-ati ranger htop neofetch i3-gaps powerline i3lock i3status tmux plasma-meta xfce4 xfce4-goodies volumeicon pulseaudio alsa-utils pulseaudio-alsa feh okular nitrogen w3m sxiv xsel zsh git wget subversion make fakeroot sddm/lightdm lightdm-gtk-greeter firefox adapta-gtk-theme papirus-icon-theme archlinux-wallpaper xdg-user-dirs rxvt-unicode urxvt-perls mpv youtube-dl mpd ncmpcpp libsidplay xarchiver engrampa ttf-hack mlocate mutt pavucontrol cowsay fortune-mod awesome bspwm sxhkd dmenu rofi lxappearance redshift imagemagick gimp inkscape gpick espeak net-tools blueman bluez bluez-libs pulseaudio-bluetooth meson ninja vala grub gtk-engine-murrine gst-plugins-base gst-plugins-good gst-plugins-bad gst-plugins-ugly java-runtime-common java-environment-common jre-openjdk dolphin ffmpegthumbs dolphin-plugins mpd gparted konsole arandr hwinfo ttf-roboto noto-fonts accountsservice xf86-video-fbdev xf86-video-vesa xf86-video-intel (vm: virtualbox-host-modules-arch or virtualbox-guest-dkms virtualbox-guest-iso xf86-video-vmware) kde-gtk-config qemu dnsmasq

### Microcode
- pacman -S amd-ucode intel-ucode

### Add User
- groupadd usb (vbox, etc.)
- useradd -m -G wheel,audio,optical,storage,video,games,power,scanner -s /bin/zsh chris
- passwd chris
- vi /etc/sudoers
```
\-- # %wheel ALL=(ALL) ALL
++ %wheel ALL=(ALL) ALL
```

### Enable basic services
- systemctl enable sddm.service
- systemctl enable NetworkManager.service
- Reboot

### AUR
- git clone https://aur.archlinux.org/trizen.git
- cd trizen
- makepkg -si
- trizen -S breeze-adapta-theme-git archlinux-themes-sddm fortune-mod-hitchhiker fbterm-git dwm-git pamac-aur pamac-tray-appindicator stardict task-spooler yank clipit yad mate-tweak simplenote-electron-bin ttf-ms-fonts gamemode cantata adwaita-dark highlight perl-json-xs

### AUR Change Clone Directory
- trizen -S [Package] --clone-dir=$HOME/.sources/Trizen_tmp

### Restart & Shutdown hangups
- edit /etc/sudoers
```
++ chris ALL=NOPASSWD: /sbin/restart, /sbin/poweroff
```

### Plasma Double-click to open files and folders
- Settings -> Desktop Behavior -> Workspace -> Click Behavior (Plasma 5.16.4 | 2019)

### Virtualbox Guest
- systemctl enable vboxservice.service

### Fonts
- cd /etc/fonts/conf.d/
- sudo rm /etc/fonts/conf.d/10(asterisk)********** && sudo rm -rf ./70-no-bitmaps.conf && sudo ln -s ../conf.avail/70-yes-bitmaps.conf
- mkdir ~/.local/share/fonts && cd ~/.local/share/fonts
- wget https://raw.githubusercontent.com/NerdyPepper/scientifica/master/regular/scientifica-11.bdf
- wget https://raw.githubusercontent.com/NerdyPepper/curie/master/regular/curieMedium-12.bdf
- wget https://raw.githubusercontent.com/NerdyPepper/curie/master/bold/curieBold-12.bdf
- wget https://raw.githubusercontent.com/NerdyPepper/curie/master/italic/curieItalic-12.bdf
- fc-cache -f

### xdg-user-dirs
- xdg-user-dirs-update

### Printing
- pac -S cups (and drivers)
- sudo systemctl enable org.cups.cupsd.service
- Manage with: http://localhost:631

### Early KMS
- pacman -S read-edid
- mkdir /usr/lib/firmware/edid
- (root) get-edid -m 0 > /usr/lib/firmware/edid/800x600.bin
- vi /etc/mkinitcpio.conf
```
++ MODULES=(radeon)
++ FILES=(/usr/lib/firmware/edid/800x600.bin)
```
- mkinitcpio -c /etc/mkinitcpio.conf -g /boot/initramfs-linux.img
- grub-mkconfig -o /boot/grub/grub.cfg
- vi /etc/modprobe.d/modprobe.conf
- ++ options drm_kms_helper poll=0

### ZDM
- touch ~/.scripts/urxvt_fortune.txt
- touch ~/.xinitrc
- vi ~/.ZDM
- replace default
- echo "exec i3" > ~/.xinitrc
- sudoc ~/.ZDM
- sudoc ~/.xinitrc
- sudoc -R ~/.scripts/*

### i3lock Multi-monitors + clock
- Keep Arch pkg i3lock
- git clone https://github.com/shikherverma/i3lock-multimonitor.git
- cp -r i3lock-multimonitor ~/.i3
- chmod +x ~/.i3/i3lock-multimonitor/lock
- swap /i3lock-multimonitor/img/background.png for preferred image
- git clone https://github.com/Lixxia/i3lock.git
- cd i3lock
- autoreconf -fi
- mkdir -p build && cd build
- ../configure
- make && sudo make install

### Fbterm
- setcap 'cap_sys_tty_config+ep' $(command -v fbterm)
- usermod -aG video USERNAME

### OpenRC?
- https://blog.notfoss.com/posts/openrc-on-arch-linux/

### Turn off journaling EXT4
- umount /sdX
- tune2fs -O "^has_journal" /dev/sdXX

### Systemd Journal to RAM
- vi /etc/systemd/journald.conf.d/usbstick.conf
```
++ [Journal]
++ Storage=volatile
++ RuntimeMaxUse=30M
```

### OpenRC Logging
- vim /etc/rc.conf
```
\-- rc_logger="YES"
++ # rc_logger="YES"
```

### Alternate Shell Prompt (Bash)
- vim ~/.bashrc
```
++ export PS1="\[\e[33m\]\u\[\e[m\]@\[\e[33m\]\h\[\e[m\] [\[\e[36m\]\w\[\e[m\]] [\[\e[35m\]\d\[\e[m\] \[\e[35m\]\@\[\e[m\]]\[\e[36m\]\\$\\n-> "
```

### Input Polling Issues
- test with: sudo sh -c 'echo N > /sys/module/drm_kms_helper/parameters/poll'
- persistent change: sudo sh -c 'echo "options drm_kms_helper poll=0" >> /etc/modprobe.d/local.conf'
- sudo update-initramfs -u
- append i8042.nomux=1 to /etc/default/grub kernel params and update-grub

### Downgrading Packages
- search: https://archive.archlinux.org/packages/
- example: pacman -U https://archive.archlinux.org/packages/l/libnfs/libnfs-3.0.0-2-x86_64.pkg.tar.xz
- Wait until affected package breaks.. then upgrade again..
- or perhaps use downgrader(AUR) if you don't want to access archive.archlinux.org
    - downgrade <package> <package> <package> <package> ... follow the prompts


### Security
- pacman -S net-tools arch-audit
- sudo netstat -tulpn
- arch-audit
- arch-audit \--upgradable \--quiet

### Mesa Requires avx2 >= mesa-19.3.4-1 (2020-02-14)
- First mentioned: https://bbs.archlinux.org/viewtopic.php?id=252888
- netctl wifi guide at the top of this document..
- pac -U https://archive.archlinux.org/packages/m/mesa/mesa-19.3.3-1-x86_64.pkg.tar.zst
- sudov /etc/pacman.conf
- ++ IgnorePkg     = mesa

### ArchWiki Local Copy
- git clone https://github.com/lahwaacz/arch-wiki-docs
- python-simplemediawiki
- python-cssselect
- python-lxml
- ./arch-wiki-docs.py \--output-directory "/dir/output_directory"S

### AUR No space on device
- trizen -S <package> --clone-dir=/home/$USER/tmp/Trizen_tmp

### Create Package backups
- pacman -Qqen > /home/$USER/targetdir/pkglist.txt ## FULL PKG BACKUP!
- pacman -Sp kde > /home/$USER/targetdir/pkglist ## SINGLE PKG BACKUP
- Download packages: wget -nv -i /home/$USER/targetdir/pkglist.txt

### KDE Wallet Auto Login
- pac -S kwallet-pam
- Disable: "Close when last application stops using it" in KDE Wallet settings
- Does not work with fingerprint reader login
- If all else fails and one just needs WiFi at login: Change KDE Wallet password to a blank password

### Install RPM Packages
- Open with your favorie archive browser (Ark, ggrandpa, file-roller, etc.)
- Distribute files (pcmanfm can be opened as admin--ex: sudo pcmanfm)
- Or.. make a pkgbuild

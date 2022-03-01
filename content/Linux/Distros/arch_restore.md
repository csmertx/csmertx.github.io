## Arch Linux restore bootloader

### iwctl (wireless access)
- iwctl
  - station wlan0 (device found with: ip link) connect YOURFRIENDLYNEIGHBORHOODWIFIADDRESS
    - Enter passphrase
  - exit

### Chroot (chroot: failed to run command /usr/bin/zsh: No such file or directory)
- chroot /mnt /bin/bash

### netctl (outdated as of: 2022)
- cp /etc/netctl/examples/wireless-wpa /etc/netctl/<essid_name>
- vi /etc/netctl/<essid_name> (ip link), essid, key, etc.
- netctl start <essid_name>

### Format
- mkfs.ext4 /dev/sXX
- swapon /dev/sXX

### Base install
- (filesystem) mount /dev/sXX /mnt
- pacstrap /mnt base
- genfstab -U /mnt >> /mnt/etc/fstab
- arch-chroot /mnt
- ln -sf /usr/share/zoneinfo/TAB /etc/localtime
- hwclock --systohc
- pacman -S vim grub
- vim /etc/locale.gen (en_US.UTF-8, UTF-8)
- locale-gen
- vim /etc/locale.conf (LANG=en_US.UTF-8)
- vim /etc/hostname (add hostname)
- vim /etc/hosts (127.0.1.1 myhostname.localdomain myhostname)
- grub-install --target=i386-pc /dev/sdX (disk)
- grub-mkconfig -o /boot/grub/grub.cfg
- passwd
- exit

### Restore
- pacman -S borgbackup ranger tmux vim htop
- mkdir /Storage
- mount /dev/sdX /Storage
- tmux  (ctrl+b % or ctrl+b ")
- borg list /Storage/OS_Backups/Arch_Linux
- cd /mnt
- borg extract --dry-run --progress /Storage/OS_Backups/Arch_Linux::root-2019-xx-xx
- arch-chroot /mnt
- apend new uuid to fstab (blkid or fdisk -l)
- grub-mkconfig -o /boot/grub/grub.cfg 

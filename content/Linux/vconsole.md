---
title: Virtual Console
weight: -20
---

### Add users & add groups (/sbin/...)
- cat /etc/passwd (displays all users)
- sudo useradd -G wheel,sudo newuser
- sudo usermod -a -G existinggroup existinguser
- sudo groupadd newgroup
- usermod -a -G newgroup existinguser

### Passwd
- Unattended
    - echo "user:password" | chpasswd (only as root)
- Normal
    - passwd user
    - # passwd (root)

### Permissions
- Web Resource
    - chmodcommand.com
- Typical user RWX
    - chmod 700 (similar to chmod +x)
- Only owner has RW
    - chmod 644
- Blank out permissions
    - chmod 000
- RWX for EVERYONE
    - chmod 777 (RWX All Users & Groups)

### Use systemd to auto login (CentOS)
- sudo systemctl edit getty@tty1
- or
- sudo mkdir /etc/systemd/system/getty@tty1.service.d
- sudov /etc/systemd/system/getty@tty1.service.d/override.conf
- ++ [Service]
- ++ ExecStart=
- ++ ExecStart=-/sbin/agetty (check dir) --autologin weyoun ($USER) --noclear %I $TERM
- Reboot to check; chroot to fix

### Setting up automatic inactive user logout
- vim ~/.bash_profile
- or
- /etc/profile
- TMOUT=300 #TMOUT=<seconds>
- readonly TMOUT
- export TMOUT

### Disable Plymouth
- sudov /etc/default/grub
- Most distributions
    - -- GRUB_CMDLINE_LINUX="... splash quiet"
    - ++ GRUB_CMDLINE_LINUX="..."
- CentOS
    - -- GRUB_CMDLINE_LINUX="... rhgb quiet" #Redhat Graphical Boot
    - ++ GRUB_CMDLINE_LINUX="..."
- Most distributions
    - sudo update-grub
    - or
    - sudo grub-mkconfig -o /boot/grub/grub.cfg
CentOS
    - sudo grub2-mkconfig -o /etc/grub2.cfg (CentOS/RHEL)

### Enable Mouse Support (+copy/paste w/mouse)
- sudo package_manager_install gpm
- Select text by holding down LMB
- Paste with RMB
- Disable/Enable with: sudo /etc/init.d/gpm stop/start

### Print OS Distribution
- cat /etc/(asterisk)-release

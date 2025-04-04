---
title: 💻 Admin
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-01-30
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

> Same as [Virtual Console](/Linux/Assorted/vconsole)

# Typical Console Commands

## Add users & add groups

- ```cat /etc/passwd```

    > Displays all users

- ```sudo useradd -G wheel,sudo newuser```

- ```sudo usermod -a -G existinggroup existinguser```

- ```sudo groupadd newgroup```

- ```usermod -a -G newgroup existinguser```

## Passwd

- Unattended

    - ```echo "user:password" | chpasswd```

        > Only as root

- Normal

    - ```passwd user```

        > User passwd

    - ```sudo passwd```

        > Superuser passwd

## Permissions

> RWX == Permission to Read, Write, & eXecute

- Typical user RWX

    - ```chmod 700```

        > similar to chmod +x

- Only owner has RW

    - ```chmod 644```

- Blank out permissions

    - ```chmod 000```

- RWX for EVERYONE

    - ```chmod 777```

        > RWX All Users & Groups (risky)

## Use systemd to auto login (CentOS)

- ```sudo systemctl edit getty@tty1```

- or

- ```sudo mkdir /etc/systemd/system/getty@tty1.service.d```

- ```sudov /etc/systemd/system/getty@tty1.service.d/override.conf```

    ```
    ++ [Service]
    ++ ExecStart=
    ++ ExecStart=-/sbin/agetty (check dir) --autologin weyoun ($USER) --noclear %I $TERM
    ```

- Reboot to check; or chroot to fix

## Setting up automatic inactive user logout

- ```vim ~/.bash_profile```

- or

- ```sudov /etc/profile```

    ```
    TMOUT=300 #TMOUT=<seconds>
    readonly TMOUT
    export TMOUT
    ```

## Disable Plymouth

- ```sudov /etc/default/grub```

- Most distributions

    ```
    -- GRUB_CMDLINE_LINUX="... splash quiet"
    ++ GRUB_CMDLINE_LINUX="..."
    ```

    > ... Typically required to boot system
    
- CentOS

    ```
    - -- GRUB_CMDLINE_LINUX="... rhgb quiet" #Redhat Graphical Boot
    - ++ GRUB_CMDLINE_LINUX="..."
    ```

- Most distributions

    - ```sudo update-grub```

    - or

    - ```sudo grub-mkconfig -o /boot/grub/grub.cfg```

- CentOS

    - ```sudo grub2-mkconfig -o /etc/grub2.cfg```

        > CentOS/RHEL

## Enable Mouse Support (+copy/paste w/mouse)

- ```sudo package_manager_install gpm```

    - Select text by holding down ```LMB```

    - Paste with ```RMB```

    - Disable/Enable with: ```sudo /etc/init.d/gpm stop/start```

## Print OS Distribution

```cat /etc/*-release```

## Resources

- [Chmod Calculator](https://chmodcommand.com/)

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 01/07/2023 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Assorted/admin.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Assorted \ Admin">
       History 🕵️
    </a>
</div>
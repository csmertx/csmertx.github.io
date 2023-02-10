---
title: OpenSSH
author: csmertx
date: February 4, 2023
weight: -20
---

## Hardening (see also: fail2ban)

- ```sudov /etc/ssh/sshd_config```

    ```
    ++ PermitRootLogin no
    ```

## Logs

- ```sudo tail -n 50 /var/log/auth.log```

## Basic Local SSH (BAD--but handy for throw away local VMs)

- ```ssh -p 22 user@192.168.254.x```

    - ```[Enter Password]```

- ```apt-get install sshpass```

- ```sshpass -p your_password ssh user@192.168.254.x```

- Script it

    - ```gpg --full-generate-key```

    - ```mkdir $HOME/.passcrypt```

    - ```vim ssh (create password file)```

    - ```gpg --encrypt $HOME/.passcrypt/ssh.gpg```

        ```
        #!/bin/bash
        sshpassw="$(gpg -d $HOME/.passcrypt/ssh.gpg |)"
        sshpass -p $sshpassw ssh user@192.168.254.x
        ```

- See also: [fail2ban](/Linux/Software/fail2ban) & [iptables](/Linux/Software/iptables)

## Copy Files

- From Remote to local

    - ```scp username@b:/path/to/file /path/to/destination```

- From local to remote

    - ```scp /path/to/file username@b:/path/to/destination```

## Copy Directories

- ```scp -prq username@host:/path/to/file/ /path/to/destination/```

- ```scp -prq /path/to/file/ username@host:/path/to/destination/```

## Run X Programs on remote

- Setup

    - ```export DISPLAY:=0```

- Send keyboard keys to GUI apps

    - ```xdotool key --window "$(xdotool search --class mpv)" p```

## Mount Filesystems from remote

- ```mkdir /mnt/destination```

- ```sshfs user@host:/source /mnt/destination```

- ```cd /mnt/destination```

## Mount Filesystems to remote

- ```mkdir /mnt/destination```

- ```sshfs /source user@host:/destination```

- ```cd /mnt/destination```

### Fish Network Protocol

- Dolphin File Browser: ```fish://user@xxx.xxx.xxx```

- MC: ```cd sh://user@xxx.xxx.xxx```

- Similar to Secure FTP

## Remote Linux filesystem with Windows Explorer

> Edit files with [VSCode](https://code.visualstudio.com/), etc.

- Powershell
    
    - ```winget install WinFsp.WinFsp; winget install SSHFS-Win.SSHFS-Win```

- [Download latest sshfs-win-manager-setup](https://github.com/evsar3/sshfs-win-manager/releases/tag/v1.3.1)

- Links to projects [below](#resources)

## Passwordless login (bad)

- ```ssh-keygen -t rsa -b 4096 -C "your_email@domain.com" #username@reminder.com```

    - Press enter for all entries

- ```ssh-copy-ide remote@remotesystem```

## Passwordless login (it's probaby fine)

- ```eval $(ssh-agent)```u

- ```ssh-add```

    - OR: ```ssh-add /home/user/.ssh/id_(...)```

    - OR ```ssh-add /home/user/.ssh/id_superdupersshkey```

- Enter ```password```

- ```vim``` (or ```nano```) ```~/.profile```

    - ```eval "$(ssh-agent)"```
    
        > For persistence between logins

## Resources

- [Stack Overflow: Git always asks for my ssh-key passphrase](https://stackoverflow.com/questions/31377629/git-always-asks-for-my-ssh-key-passphrase)

- [Total Commander: Cross-platform file manager](https://www.ghisler.com/androidapp.htm)

    > Android file manager with option for secure FTP (SSH) (plugin)

- [GitHub - evsar3/sshfs-win-manager: A GUI for SSHFS-Win](https://github.com/evsar3/sshfs-win-manager)

- [Github - sshfs-win/README.md at master](https://github.com/winfsp/sshfs-win/blob/master/README.md)
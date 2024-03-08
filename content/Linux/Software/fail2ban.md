---
title: 💻 Fail2ban
author: csmertx
date: February 3, 2023
weight: -20
---

<br />

## Setup

- Systemd

    - ```sudo systectm enable fail2ban.service```

    - ```sudo systectm start fail2ban.service```

- SSH Limiting

- ```sudov /etc/fail2ban/jail.d/sshd.local```

    ```
    ++ [sshd]
    ++ enabled    = true
    ++ filter     = sshd
    ++ banaction  = ufw
    ++ backend    = systemd
    ++ maxretry   = 3
    ++ findtime   = 1h
    ++ bantime    = 2h
    ++ ignoreip   = 127.0.0.1/8 10.0.0.0/8 172.16.0.0/12 192.168.0.0/16
    ```

    - ```sudo systectm restart fail2ban.service```

## Client

- ```sudo fail2ban-client status```

    > List all jails

- ```sudo fail2ban-client status sshd```

    > Status of jails

## Resources

- [Fail2ban](https://www.fail2ban.org/wiki/index.php/Main_Page)

- [Red Hat: Linux security: Protect your systems with fail2ban](https://www.redhat.com/sysadmin/protect-systems-fail2ban)
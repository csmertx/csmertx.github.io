---
title: 💻 Fail2ban
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-03
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

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

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Software/fail2ban.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Software \ Fail2ban">
       History 🕵️
    </a>
</div>
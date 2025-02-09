---
title: 💻 iptables
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-03
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Start and configuration

- Systemd

    - ```sudo systemctl enable iptables.service```

    - ```sudo systemctl start  iptables.service```

    - ```sudo systemctl restart iptables.service```
    
        > After edits

- Port forwarding

    - ```sudo iptables -P FORWARD DROP```

## Gufw

- Systemd

    - ```sudo systemctl enable ufw.service```

    - ```sudo systemctl start ufw.service```

- SSH Limiting

    - Add rule

        - Subcat: Services

        - Application: SSH

        - Policy: Limit

## Ufw

- Port forwarding

    - ```sudov /etc/ufw/sysctl.conf```

        - Uncomment..

            ```
            #net/ipv4/ip_forward=1
            #net/ipv6/conf/default/forwarding=1
            #net/ipv6/conf/all/forwarding=1
            ```

- ```sudo ufw reload```

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Software/iptables.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Software \ iptables">
       History 🕵️
    </a>
</div>
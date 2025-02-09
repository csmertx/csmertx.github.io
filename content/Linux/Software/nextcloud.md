---
title: 💻 Nextcloud
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-04
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## WebDav
- File manager
    - ```webdav://192.168.254.xx/remote.php/webdav/```

## Restart All Services
- ```sudo systemctl restart redis.service php-fpm.service nginx.service```

## Update through CLI

- ```sudo -u http php /usr/share/nginx/nextcloud/updater/updater.phar```

- ```sudo -u http php /usr/share/nginx/nextcloud/occ update```

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Software/nextcloud.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Software \ Nextcloud">
       History 🕵️
    </a>
</div>
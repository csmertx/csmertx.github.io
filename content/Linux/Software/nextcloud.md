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

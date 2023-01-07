---
title: Nextcloud
weight: -20
---

### WebDav
- File manager
    - webdav://192.168.254.xx/remote.php/webdav/

### Restart All Services
- sudo systemctl restart redis.service \
    php-fpm.service nginx. service

### Update through CLI
- $HOME/.scripts/nextcloudu # This moves static files served by Nginx
- sudo -u http php /usr/share/nginx/nextcloud/updater/updater.phar
- sudo -u http php /usr/share/nginx/nextcloud/occ update

---
title: Crontab > Cron Job Management
weight: -20
---

### To edit..
- crontab -e (user only)
- sudo crontab -e (global)

### IDGAF WYSIWYG
- https://crontab.guru

### Gist
```
*   *          *           *     *
min hour(24hr) day (month) month day (week)
```
- Example: 02 12 * * * <command> == run <command >once at 10:05PM everyday
- Simple: minute hour (24hr)

### Location
- /var/spool/cron

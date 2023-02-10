---
title: Bitmap Fonts
author: csmertx
date: January 30, 2023
weight: -20
---

## Enable bitmap fonts (Debian/Ubuntu)

- ```sudo rm -f /etc/fonts/conf.d/70-{yes,no,force}-bitmaps.conf```

```
if test -f /etc/fonts/conf.avail/70-force-bitmaps.conf; then
    sudo ln -s {../conf.avail,/etc/fonts/conf.d}/70-force-bitmaps.conf
else sudo ln -s {../conf.avail,/etc/fonts/conf.d}/70-yes-bitmaps.conf
fi
```

- ```sudo rm -rf /var/cache/fontconfig/(star)```

- ```rm -rf "$HOME/.fontconfig"```

- ```sudo fc-cache```

- ```fc-cache```

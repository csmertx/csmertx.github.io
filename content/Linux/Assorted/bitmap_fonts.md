---
title: 💻 Bitmap Fonts
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-01-30
weight: -20
---

<br />

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

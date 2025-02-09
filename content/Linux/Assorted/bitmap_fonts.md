---
title: 💻 Bitmap Fonts
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-01-30
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

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

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 01/07/2023 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Assorted/bitmap_fonts.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Assorted \ Bitmap Fonts">
       History 🕵️
    </a>
</div>

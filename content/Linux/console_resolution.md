---
title: Console Resoluation
weight: -20
---

### Source link: 
https://askubuntu.com/questions/18444/how-do-i-increase-console-mode-resolution

### Editing files...
```sudov /etc/default/grub```
```++ GRUB_GFXMODE=1152x864x32```
```++ GRUB_GFXPAYLOAD=1152x864x32```

```sudov /etc/grub.d/00_header```
```-- if [ "x${GRUB_GFXMODE}" = "x" ] ; then GRUB_GFXMODE=auto ; fi```
```++ if [ "x${GRUB_GFXMODE}" = "x" ] ; then GRUB_GFXMODE=1152x864x32 ; fi```
```++ if [ "x${GRUB_GFXPAYLOAD}" = "x" ] ; then GRUB_GFXPAYLOAD=1152x864x32 ; fi```

Find: ```set gfxmode=${GRUB_GFXMODE}```
Next line: ```set gfxpayload=${GRUB_GFXPAYLOAD}```


---
title: Console Resolution
author: csmertx
date: January 30, 2023
weight: -20
---

<br />

> See also [Virtual Console](/Linux/Assorted/vconsole)

## Editing files...

- ```sudov /etc/default/grub```

    ```
    ++ GRUB_GFXMODE=1152x864x32
    ++ GRUB_GFXPAYLOAD=1152x864x32
    ```

- ```sudov /etc/grub.d/00_header```

    ```
    -- if [ "x${GRUB_GFXMODE}" = "x" ] ; then GRUB_GFXMODE=auto ; fi
    ++ if [ "x${GRUB_GFXMODE}" = "x" ] ; then GRUB_GFXMODE=1152x864x32 ; fi
    ++ if [ "x${GRUB_GFXPAYLOAD}" = "x" ] ; then GRUB_GFXPAYLOAD=1152x864x32 ; fi
    ```

- Look for: ```set gfxmode=${GRUB_GFXMODE}```

    > / to input a search term with Vim

- Next line: ```set gfxpayload=${GRUB_GFXPAYLOAD}```

## Resources

- [Ask Ubuntu: "How do I increase console-mode resolution?"](https://askubuntu.com/questions/18444/how-do-i-increase-console-mode-resolution)


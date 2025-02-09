---
title: 💻 Console Resolution
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-01-30
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

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

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 01/07/2023 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Assorted/console_resolution.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Assorted \ Console Resolution">
       History 🕵️
    </a>
</div>
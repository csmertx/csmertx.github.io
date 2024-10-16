---
title: 💻 XScreenSaver
author: Chris Schammert (csmertx)
published: 2023-02-04
weight: -20
---

<br />

> XScreenSaver Multi-monitor Patch

> See [patching](/Linux/Software/patching) to use this patch

```
$ diff screens-original.c screens.c
387a388,389
>       /* one hack over multi-monitor patch - blatantly overrule what randr thinks */
>       nscreens = 1;
450c452,453
<           for (k = 0; k < res->noutput; k++, j++)
---
>         /* one hack over multi-monitor patch - ignore randr number of outputs, force 1 */
>         for (k = 0; k < 1; k++, j++)
469,472c472,476
<                   m->x      = crtci->x;
<                   m->y      = crtci->y;
<                   m->width  = crtci->width;
<                   m->height = crtci->height;
---
>                   /* one hack over multi-monitor patch - hardcoded resolution for this workstation's "single" screen */
>                   m->x      = 0;
>                   m->y      = 0;
>                   m->width  = 5920;
>                   m->height = 1440;
574,582c578
<   else if (   randr_monitors[0] &&   !randr_monitors[1] &&  /* 1 monitor */
<            xinerama_monitors[0] && xinerama_monitors[1])    /* >1 monitor */
<     {
<       *errP = append (*errP,
<                       "WARNING: RANDR reports 1 screen but Xinerama\n"
<                       "\t\treports multiple.  Believing Xinerama.");
<       free_monitors (randr_monitors);
<       return xinerama_monitors;
<     }
---
>   /* one hack over multi-monitor patch - force xscreensaver to use our hardcoded RANDR details, not xinerama */
```

## Resources

- [XScreenSaver](https://www.jwz.org/xscreensaver/)

- [SNARGAWOK: Forcing xscreensaver to display one hack over multiple monitors.](https://www.jabawok.net/?p=158)


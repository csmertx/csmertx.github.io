"So xscreensaver’s author Jamie Zawinski has previously stated he thinks most of the hacks look bad stretched across multiple monitors Around about version 4.12, multi monitor support turned into “one hack per screen”. After going through the large list of hacks, I thoroughly disagree. Most of them look really good, and some of them – like the above depicted “lattice” look stunning – especially at buttery smooth 144hz.

The following patch against drivers/screens.c in xscreensaver v5.40 make this possible in my setup. The resolution is hard-coded – I hope in the future I can convince Jamie or one of the other maintainers to implement a more elegant solution. In essence we’re fooling xscreensaver into thinking theres 1 big screen – 5920 x 1440 (with a few wasted pixels due to the mismatched screen resolutions in my case)."

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

Sourced: https://www.jabawok.net/?p=158


=> vim ~/.config/openbox/menu.xml

```
<?xml version="1.0" encoding="utf-8"?>
<openbox_menu>
    <menu id="root-menu" label="OpenBox 3" execute="/usr/bin/obmenu-generator">
    </menu>
</openbox_menu>
```

=> vim ~/.config/openbox/rc.xml

```
  <placement>
    <policy>Smart</policy>
    <!-- 'Smart' or 'UnderMouse' -->
    <center>yes</center>
    <!-- whether to place windows in the center of the free area found or
       the top left corner -->
    <monitor>Any</monitor>
    <!-- with Smart placement on a multi-monitor system, try to place new windows
       on: 'Any' - any monitor, 'Mouse' - where the mouse is, 'Active' - where
       the active window is -->
  </placement>
``` 

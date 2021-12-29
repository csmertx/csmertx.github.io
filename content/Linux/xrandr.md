### Mode Not Displayed
- cvt 1600 900
- Copy line that starts with Modeline
- sudo xrandr --newmode ...copied line minus the word Modeline...
- sudo xrandr --addmode {vga,Virtual}-{0,1} "1600x900_60.00" #Virtual-1
- sudo xrandr --output Virtual-1 --mode "1600x900_60.00"
- arandr or System Settings > Display > select new option: 1600x900

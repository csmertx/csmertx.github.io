---
title: 💻 Find
author: Chris Schammert (csmertx)
published: 2023-01-31
weight: -20
---

<br />

> Does not create databases accessible to other users (e.g. locate command)

## Print subdirectories or files in a directory

- ```cd $targetdir && find . -maxdepth 1 -mindepth 1 -type d -printf "%f"```

## Scripting example

> ~/.scripts/sudof

```
#!/bin/bash

# Skips Arch Linux package cache, home directory, etc.
dirs_exclude="-path /mnt -o -path /run -o -path /tmp -o -path /dev -o -path /proc -o -path \
$HOME -o -path /sys -o -path /var/cache/pacman -o -path /var/lib/pacman"

sudo find / -type d \( $dirs_exclude \) -prune -o -print | grep $1
```
- ```echo -en "alias sudof='~/.scripts/sudof'" >> ~/.bashrc```

- ```sudof blah```

## Resources

- [Findutils: basic searching utilities of the GNU operating system](https://www.gnu.org/software/findutils/)
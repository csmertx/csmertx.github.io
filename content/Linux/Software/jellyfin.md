---
title: 💻 Jellyfin (Media Server)
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-04-01
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Install Docker

- ```apti snapd```

- ```sudo snap install docker```

    > Yep, container in a container. But it works!

- ```sudo docker pull jellyfin/jellyfin```

- ```mkdir ~/.config/jellyfin```

- ```mkdir ~/.config/jellyfin/config```

- ```mkdir ~/.config/jellyfin/cache```

## Server start

> First run will take a while to cache (20-60+ minutes)

```
sudo docker run -d \
--volume /home/$USER/.config/jellyfin/config:/config \
--volume /home/$USER/.config/jellyfin/cache:/cache \
--volume /mnt/Storage/Videos:/data/videos \
--volume /mnt/Storage/Music:/data/music \
--volume /mnt/Storage/Pictures:/data/pictures \
--user 1000:1000 \
--net=host \
--restart=unless-stopped \
jellyfin/jellyfin
```

## Scripted setup

> My personal setup script

```
!#/bin/bash
# jellyfin_setup.sh

sudo docker run -d \
--volume /home/$USER/.config/jellyfin/config:/config \
--volume /home/$USER/.config/jellyfin/cache:/cache \
--volume /mnt/Storage/Videos:/data/videos \
--volume /mnt/Storage/Music:/data/music \
--volume /mnt/Storage/Pictures:/data/pictures \
--user 1000:1000 \
--net=host \
--restart=unless-stopped \
jellyfin/jellyfin
```

## Server stop

- ```sudo docker ps```

- ```sudo docker stop [CONTAINER ID]```

## Update

- ```sudo aa-remove-unknown```

    > You may want to 🔗 [read](https://forum.snapcraft.io/t/broken-apparmor/32191 "Snapcraft.io | Forum \ Broken Apparmor") about the repercussions of ```aa-remove-unknown``` before continuing.

- ```sudo docker ps```

- ```sudo docker stop [CONTAINER ID]```

- ```sudo docker pull jellyfin/jellyfin```

- ```$HOME/.scripts/jellyfin_setup.sh```

    > The script I use can be found 🔗 [here](https://github.com/csmertx/dotfiles/blob/master/scripts/jellyfin_setup.sh "Github.com | csmertx \ dotfiles \ scripts \ jellyfin_setup.sh")

## Restart after system update

- ```$HOME/.scripts/jellyfin_setup.sh```

## Restart Docker/Jellyfin

- ```sudo docker ps```

- ```sudo docker restart [CONTAINER ID]```

## Error submitting packet to decoder: Invalid data found when processing input

- Certain container formats may throw this error with 🔗 [VA-API](https://en.wikipedia.org/wiki/Video_Acceleration_API "Wikipedia | Video Acceleration API") hardware encoding enabled (AMD GPU).

    - Confirm by toggling hardware encoding off via: Hamburger > Dashboard > Playback > Transcoding

## Resources

- [Jellyfin: The Free Software Media System](https://jellyfin.org)

- [GitHub - jellyfin/jellyfin: The Free Software Media System](https://github.com/jellyfin/jellyfin)

- [Wikipedia - Video Acceleration API](https://en.wikipedia.org/wiki/Video_Acceleration_API)

---
title: 💻 Music Player Daemon (MPD)
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-04
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

> Includes some instructions to listen to Commodore 64 .sid files

## Requires

- ```mpd-sidplay```

- ```mpc```

- [DeaDBeeF](#resources) (optional for .sid playlist creation)

- Debian for .sid songlengths

    > Easier listening experience

## mpdconf.example

- ```mkdir ~/.config/mpd```

- ```cp /usr/share/doc/mpd/mpdconf.example ~/.config/mpd/mpd.conf```

## Local Permissions

- ```sudo gpasswd -a mpd $USER```

- ```sudo chmod 710 /home/$USER```

## Local Configuration

```
music_directory       "/home/user/Music"
user                 "user" #Without systemd
group                 "user" #Without systemd
bind_to_address        "/home/user/.config/mpd/mpd.socket"
pid_file              "/home/user/.config/mpd/pid"
db_file               "/home/user/.config/mpd/db" # MPD will create this..
state_file            "/home/user/.config/mpd/state"
playlist_directory    "/home/user/.config/mpd/playlist"
log_file              "/home/user/.config/mpd/mpd.log"
sticker_file          "/home/user/.config/mpd/sticker.sql" # MPD will create this..
restore_paused        "yes"
auto_update           "yes"
```

## Commodore 64 music file playback (.sid extension)
- ```tri -S mpd-sidplay```

    - Add to ```mpd.conf```

        ```
            decoder {
               plugin "sidplay"
               songLength_database "/dir/file.txt or /dir/file.md5"
               default_songlength "seconds (180)"
               filter "true"                                                                                         
            }
        ```

## Load MPD

- ```sudo systemctl disable mpd```

- ```sudo pkill mpd```

- ```mpd /home/user/.config/mpd/mpd.conf```

## Setup database

- DeaDBeeF > File > New Playlist > File > Add Folders > File > Save Playlist (m3u)

    > DeaDBeeF music player compiled for Debian is bundled with .sid support

- ```mpc -h /home/user/.config/mpd/mpd.socket load /dir/playlist.m3u```

- ```mpc -h /home/user/.config/mpd/mpd.socket update```

## NCMPCPP: MPD client compatible with mopidy

- Make sure port is set (default)

- ```bind_to_address``` as well

- ```apti ncmpcpp```

- ```ncmpcpp```

    > I think this was to load music from a folder? I haven't used NCMPCPP since ~2018

    - ```TAB```

    - ```SPACE``` to include directory

    - ```TAB``` You have songs


## Resources

- [Music Player Daemon (MPD)](https://www.musicpd.org/)

- [NCurses Music Player Client (Plus Plus) (NCMPCPP)](https://rybczak.net/ncmpcpp/)

- [DeaDBeeF: Modular cross-platform audio player](https://deadbeef.sourceforge.io/)

- [High Voltage SID Collection (HVSC)](https://www.hvsc.c64.org/)

    > Community created .sid tunes from the 1980s to 2020s

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Software/mpd.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Software \ Music Player Daemon (MPD)">
       History 🕵️
    </a>
</div>
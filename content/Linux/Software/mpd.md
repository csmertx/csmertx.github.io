### Requires
- mpd-sidplay
- mpc
- deadbeef
- Patience
- Perhaps Debian for songlengths..

### mpdconf.example
- mkdir ~/.config/mpd
- cp /usr/share/doc/mpd/mpdconf.example ~/.config/mpd/mpd.conf

### Local Permissions
- sudo gpasswd -a mpd $USER
- sudo chmod 710 /home/$USER

### Local Configuration
- music_directory       "/home/chris/Music"
- user                 "chris" #Without systemd
- group                 "chris" #Without systemd
- bind_to_address        "/home/chris/.config/mpd/mpd.socket"
- pid_file              "/home/chris/.config/mpd/pid"
- db_file               "/home/chris/.config/mpd/db" # MPD will create this..
- state_file            "/home/chris/.config/mpd/state"
- playlist_directory    "/home/chris/.config/mpd/playlist"
- log_file              "/home/chris/.config/mpd/mpd.log"
- sticker_file          "/home/chris/.config/mpd/sticker.sql" # MPD will create this..
- restore_paused        "yes"
- auto_update           "yes"

- C64 Music (sidplay/HVSC, etc.)
- tri -S mpd-sidplay
- Add to mpd.conf
```
    decoder {
       plugin "sidplay"
       songLength_database "/dir/file.txt or /dir/file.md5"
       default_songlength "seconds (180)"
       filter "true"                                                                                                                                           }
```

### Load MPD
- sudo systemctl disable mpd
- sudo pkill mpd
- mpd /home/chris/.config/mpd/mpd.conf

### Setup database
- Deadbeef > File > New Playlist > File > Add Folders > File > Save Playlist (m3u)
- mpc -h /home/chris/.config/mpd/mpd.socket load /dir/playlist.m3u
- mpc -h /home/chris/.config/mpd/mpd.socket update

### NCMPCPP
- Make sure port is set (default)
- bind_to_address as well
- [TAB]
- [SPACE] to include directory
- [TAB] You have songs

---
title: MPV: Video Player
weight: -20
---

### Multiple Monitors
- Autostart on monitor N
    - screen=N #(=0..)

### Mpris Integration
- https://github.com/hoyon/mpv-mpris/releases
    - mpris.so
        - Save as > ~/.config/mpv/scripts

### Firefox Extension
- https://addons.mozilla.org/en-US/firefox/addon/ff2mpv/
    - git clone https://github.com/woodruffw/ff2mpv
        - mkdir $HOME/.mozilla/native-messaging-hosts
        - cp ff2mpv.json $HOME/.mozilla/native-messaging-hosts/ff2mpv.json
            - vim $HOME/.mozilla/native-messaging-hosts/ff2mpv.json
                - ++ path: /home/chris/.config/mpv/ff2mpv.py,
        - cp ff2mpv.py $HOME/.config/mpv/ff2mpv.py
        - sudoc $HOME/.config/mpv/ff2mpv.py
    - Right click a video link and open with mpv
    - Or visit a YT video and click plugin

### Playback limiting
- ytdl-formate=bestvideo[height<=?480][vcodec!=vp9]+bestaudio/best # 720/1080/...
- Comment out for auto best quality (4K, though some creators are uploading 8K..)

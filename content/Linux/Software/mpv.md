---
title: MPV
author: csmertx
date: February 4, 2023
weight: -20
---

# MPV: A free, open source, and cross-platform media player

## Multiple Monitors

- Autostart on monitor X

- ```vim /home/user/.config/mpv/mpv.conf```

    ```
    ++ screen=X
    ```
    
    > e.g. screen=1, ```xrandr``` for a list of screens)

## Mpris Integration (desktop notifications, current media info, etc.)

- ```https://github.com/hoyon/mpv-mpris/releases```

    - ```mpris.so```

        - Save as: ```~/.config/mpv/scripts```

## Firefox Extension

- ```https://addons.mozilla.org/en-US/firefox/addon/ff2mpv/```

    - ```git clone https://github.com/woodruffw/ff2mpv```

        - ```mkdir $HOME/.mozilla/native-messaging-hosts```

        - ```cp ff2mpv.json $HOME/.mozilla/native-messaging-hosts/ff2mpv.json```

            - ```vim $HOME/.mozilla/native-messaging-hosts/ff2mpv.json```

                ```
                ++ path: /home/chris/.config/mpv/ff2mpv.py,
                ```

        - ```cp ff2mpv.py $HOME/.config/mpv/ff2mpv.py```

        - ```sudoc $HOME/.config/mpv/ff2mpv.py```

    - Right click a video link and open with mpv

    - Or visit a YT video and click plugin

## Playback preferred resolution

- ```ytdl-formate=bestvideo[height<=?480][vcodec!=vp9]+bestaudio/best```

    > 720/1080/...

- Comment out for auto best quality

## Resources

- [MPV](https://mpv.io/)

- [Qutebrowser](https://qutebrowser.org/)

    > Keyboard driven web browser with builtin methods to use external video players (MPV)

- [GitHub - qutebrowser/qutebrowser: A keyboard-driven, vim-like web browser](https://github.com/qutebrowser/qutebrowser)

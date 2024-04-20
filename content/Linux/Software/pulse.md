---
title: 💻 Pulseaudio
author: Chris Schammert (csmertx)
date: February 4, 2023
weight: -20
---

<br />

## All Systems

- ```sudo systemctl enable avahi-daemon.service```

- ```sudo systemctl start avahi-daemon.service```

## Server(s)

- ```sudov /etc/pulse/default.pa```

    ```
    load-module module-esound-protocol-tcp
    load-module module-native-protocol-tcp
    load-module module-zeroconf-publish
    ```

## Client(s)

- ```sudov /etc/pulse/default.pa```

    ```
    load-module module-esound-protocol-tcp
    load-module module-native-protocol-tcp
    load-module module-zeroconf-publish (or -discover...)
    ```

## Firewall rules

- ```tcp/4713```

    > set for Both but uni-directional is probably better?

## Trouble with pulseaudio?

- ```pulseaudio --kill```

    > daemonize with: ```pulseaudio -D```

## Buffering Issues

- ```sudov /etc/pulse/default.pa```

    ```
    -- load-module module-udev-detect
    ++ #load-module module-udev-detect
    -- load-module module-detect
    ++ load-module module-detect
    ++ load-module module-alsa-card device_id=0 tsched=true tsched_buffer_size=3145728 tsched_buffer_watermark=786432
    ```
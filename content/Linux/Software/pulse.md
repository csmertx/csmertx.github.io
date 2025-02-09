---
title: 💻 Pulseaudio
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-04
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

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

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Software/pulse.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Software \ Pulseaudio">
       History 🕵️
    </a>
</div>
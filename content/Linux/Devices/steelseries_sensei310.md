---
title: 🖱️ Sensei 310
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-01
weight: -20
---

<br />

> And other SteelSeries devices (same installation)

## Installation

- [rivalcfg: Configure SteelSeries gaming mice](https://github.com/flozz/rivalcfg)

    > Device compatibility list included in main README.md

    - ```apti cython python-dev libusb-1.0-0-dev libudev-dev libhidapi-hidraw0 python3-pip```

    - ```sudo pip3 install hidapi```

    - ```sudo pip3 install rivalcfg```

## Configuration

- Sensitivity (high/low)

    - ```rivalcfg -s 3200```

    - ```rivalcfg -S 1600```

- LED Colors

    > One of the the options is the scroll LED, the other is the logo LED

    - ```rivalcfg -c "#9EDC97" # LED off: "#000000"```

    - ```rivalcfg -C "#9EDC97" # LED off: "#000000"```

        > For various HTML color codes see [X resources](/Linux/Assorted/xresources#resources)

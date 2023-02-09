---
title: GPU
author: csmertx
date: February 1, 2023
weight: -20
---

# Display Graphics

## AMD Open Source: tear free

- ```sudov /etc/X11/xorg.conf.d/20-[GPU].conf```

    ```
    Section "Device"
        Identifier "AMD"
        Driver "radeon"
        Option "TearFree" "true"
    EndSection
    ```

    > May not be necessary for newer or more powerful cards

    > I used this option for a passively cooled Radeon 5450, and an early 00s Acer laptop

## Monitoring (CLI)

### Temperatures

- ```apti lm-sensors```

    - ```sudo sensors detect```

        > Defaults are a good start

    - ```sensors```

### AMD

> Processor load and memory usage

- ```apti radeontop```

    - Run with: ```radeontop```

### Nvidia

> Processor load and memory usage

- ```apti nvtop```

    - Run with: ```nvtop```

- ```apti nvidia-smi```

    - Run with: ```nvidia-smi```

## Monitoring (GUI)

### Nvidia

- Application: __Nvidia X Server Settings__

    - Tabs: GPU > Thermal Settings

### AMD

- Bundled with AMD Radeon drivers

    > If using open source drivers check CLI above for monitoring
---
title: 🖥️ CPUs
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-01
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Check status of Intel Mitigations

- ```grep . /sys/devices/system/cpu/vulnerabilities/*```

## Turn Off Intel Mitigations (>= 5.1.13 kernel)

> Obvious system security caveats

- ```sudov /etc/default/grub```

    ```
    ++ mitigations=off
    ```

    > At the end of kernel parameters

## Turn Off Intel Mitigations (< 5.1.13)

- ```sudov /etc/default/grub```

    ```
    ++ noibrs noibpb nopti nospectre_v2 nospectre_v1 l1tf=off nospec_store_bypass_disable no_stf_barrier mds=off
    ```

    > At the end of kernel parameters

- ```reboot```

## Monitoring

- ```apti htop```

    > More immersive than ```top```

- ```apti glances```

    > Includes sensors, HDD or SDD read/writes, CPU stats., etc.

- ```apti lm-sensors```

    - ```sudo sensors detect```

        > CPU core temperature readings, fan speed, chassis fan speed, etc.

        > Defaults options are a good start

        - Run with: ```sensors```

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Devices/cpu.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Devices \ CPUs">
       History 🕵️
    </a>
</div>
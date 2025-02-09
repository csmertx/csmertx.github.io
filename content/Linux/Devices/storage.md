---
title: 💾 Hard Disk Drives
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-01
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

> And estimating time of failure (based on arbitrary read/write cycle counts)

## Check Drive

- ```sudo smartctl -t long /dev/sdX```

    > Run test (4hr+)

- ```sudo smartctl -H /dev/sdX```

    > Print test result

## Total Writes per drive

```
echo "$(((((( $(sudo smartctl -x /dev/sdX | grep -w "Logical Sectors Written" | awk '{print ($4)}') / 2 )) / 1024 )) / 1024))GB"
```

## Total Reads per drive

```
echo "$(((((( $(sudo smartctl -x /dev/sdX | grep -w "Logical Sectors Read" | awk '{print ($4)}') / 2 )) / 1024 )) / 1024))GB"
```

## Monitor Reads/Writes

- ```apti iotop```

    - ```sudo iotop -o```

- ```apti glances```

    - ```glances```

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/19/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Devices/storage.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Devices \ Hard Disk Drives">
       History 🕵️
    </a>
</div>
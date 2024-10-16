---
title: 💾 Hard Disk Drives
author: Chris Schammert (csmertx)
published: 2023-02-01
weight: -20
---

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

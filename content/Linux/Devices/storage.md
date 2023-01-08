---
title: Storage Drives
weight: -20
---

### Check Drive
- sudo smartctl -t long /dev/sdX # test (potentially 4hr+)
- sudo smartctl -H /dev/sdX      # test result

### Total Writes per drive
- echo "$(((((( $(sudo smartctl -x /dev/sdX | grep -w "Logical Sectors Written" | awk '{print ($4)}') / 2 )) / 1024 )) / 1024))GB"

### Total Reads per drive
- echo "$(((((( $(sudo smartctl -x /dev/sdX | grep -w "Logical Sectors Read" | awk '{print ($4)}') / 2 )) / 1024 )) / 1024))GB"

### Monitor Reads/Writes
- apti iotop
- sudo iotop -o

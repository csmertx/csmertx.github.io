---
title: GPU
weight: -20
---

### Tear Free
- sudov /etc/X11/xorg.conf.d/20-[GPU].conf
- Example:
```
Section "Device"
     Identifier "AMD"
     Driver "radeon"
     Option "TearFree" "true"
EndSection
```

### AMD
- Status
    - apti amdtop
    - amdtop

### Nvidia
- Status
    - apti nvidia-smi
    - nvidia-smi

---
title: CPU
weight: -20
---

### Check status of Intel Mitigations
- grep . /sys/devices/system/cpu/vulnerabilities/(asterisk)

### Turn Off Intel Mitigations (>= 5.1.13)
- sudov /etc/default/grub
- add kernel param: mitigations=off

### Turn Off Intel Mitigations (< 5.1.13)
- sudov /etc/default/grub
- add kernel params:
    - noibrs noibpb nopti nospectre_v2 nospectre_v1 l1tf=off nospec_store_bypass_disable no_stf_barrier mds=off

---
title: Time (Clock)
weight: -20
---

### Set Local Time
- Easy
    - tzselect (user)
    - sudo tzselect (global)
    - reboot (if VM; then host too)
- Normal
    - sudo cp /usr/share/zoneinfo/America/New\_York /etc/localtime
    - vim /etc/sysconfig/clock
        - ++ ZONE="America/New_York"
    - sudo hwclock --utc -s
    - reboot (if VM; then host too)

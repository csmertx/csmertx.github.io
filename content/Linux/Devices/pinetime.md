---
title: PineTime
weight: -20
---

## PineTime Open Source Smartwatch
Less than $60 smartwatch that does not collect data. Or, a less than $60 smartwatch that is more reliable than any other Android smartwatch in that price range. Mine was shipped and on my wrist within a month (03/23/22 - 04/06/22).


### Upgrade firmware to 1.11.x via computer (external watch faces, etc.)
- Download .deb from ITD releases
- Download InfiniTime dfu and resources from InfiniTime 1.11.x release
```
systemctl --user start itd
```
```
systemctl --user enable itd
```
- Connect PineTime watch to PC bluetooth
```
itctl fw upg -a ~/Downloads/pinetime-mcuboot-app-dfu-1.11.0.zip -r ~/Downloads/infinitime-resources-1.11.0.zip
```


### Shown with Barton 20mm watchband (tight fit)

<div style="text-align: center;">
<img src="/Linux/Devices/images/pinetime_230122_front.jpg"/>
<img src="/Linux/Devices/images/pinetime_230122_version.jpg"/>
<img src="/Linux/Devices/images/pinetime_230122_back.jpg"/>
<img src="/Linux/Devices/images/pinetime_230122_main.jpg"/>
<img src="/Linux/Devices/images/pinetime_230122_apps_pg1.jpg"/>
<img src="/Linux/Devices/images/pinetime_230122_apps_pg2.jpg"/>
<img src="/Linux/Devices/images/pinetime_230122_settings_pg1.jpg"/>
<img src="/Linux/Devices/images/pinetime_230122_settings_pg2.jpg"/>
<img src="/Linux/Devices/images/pinetime_230122_settings_pg3.jpg"/>
</div>


### Resources
- [PineTime Store](https://www.pine64.org/pinetime/)
- [PineTime Wiki](https://wiki.pine64.org/index.php/PineTime)
- [InfiniTime Homepage](https://infinitime.io/)
- [InfiniTime Releases](https://github.com/InfiniTimeOrg/InfiniTime/releases)
- [ITD (Starting daemon, etc.)](https://gitea.arsenm.dev/Arsen6331/itd)
- [ITD (Releases)](https://gitea.arsenm.dev/Arsen6331/itd/releases)

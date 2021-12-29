## Retropie on RPi4 w/Official 7in LCD & WM8860 soundcard

### First steps
- Installer resizes to fit the micro SD card
- Place games in pi/roms/<game_folders_of_choice>
- Place bios in pi/BIOS
- Access console/shell (TTY) after boot with keyboard combo: CTRL + ALT + F4
- sudo raspi-config
- Chance localization and keyboard mapping (Localisation Options (for both))

### WiFi
- cd Retropie-Setup
- sudo ./retropie_setup.sh
- C Configuration / Tools
- 843 wifi - Configure WiFi

### Force WiFi to use 5Ghz (if needed)
- check with wavemon first: wavemon
- sudo iwconfig wlan0 freq 5.7G

### Download Pre-requisites
- sudo apt-get install build-essential git cabextract curl linux-headers-rpi

### Xbox One Wireless DONGLE
- sudo apt install default-jre libusb-1.0-0-dev libusb-1.0-0 cabextract
- git clone https://github.com/medusalix/xow.git
- cd xow
- make BUILD=RELEASE
- sudo make install
- sudo systemctl enable xow
- reboot
- The following to update or uninstall xow
    - sudo systemctl stop xow
    - sudo systemctl disable xow
    - sudo make uninstall
    - repeat git clone etc. (if updating)
- Configuring Layout
    - Y = X
    - X = Y
    - A = B
    - B = A

### 8Bitdo SN30 Pro Left trigger issue
- ctrl + alt + F4 (TTY Access)
- cd Retropie-Setup
- sudo ./retropie_setup.sh
- Install packages
    - xboxdrv
    - enable xboxdrv (sudo systemctl disable xow)
    - reboot
- Start as an Android controller

### wm8960 Soundcard (Seeed, XYGStudy, etc.)
- git clone https://github.com/respeaker/seeed-voicecard
    - or: https://github.com/HinTak/seeed-voicecard
- cd seeed-voicecard
- sudo ./ubuntu-prerequisite.sh (needed?)
- sudo ./install.sh --compat-kernel #(Not required from /HinTak/seeed-voicecard)
- reboot
- sudo raspi-config
    - Change soundcard to wm8960 (System Options > Sound)
- speaker-test
- Change volume
    - Access RetroPie Configuration menu via RetroPie UI
        - Audio > Mixer > F6 > seeed-2mic-voicecard
            - First speaker option changes volume
- Uninstall
    - sudo make uninstall
    - sudo ./uninstall.sh

### Overclock CPU/GPU (Keep fire extinguisher at the ready)
- sudo nano /boot/config.txt
"""
over_voltage=6
arm_freq=2147
gpu_freq=750
"""

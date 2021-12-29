## ClamAV Notes (failed: 2021-09-01)
- apti clamav clamav-daemon

### First run
- mkdir ~/.config/clamav
- mkdir ~/.config/clamav/logs
- clamconf -g freshclam.conf > ~/.config/clamav/Freshclam.conf
- clamconf -g clamd.conf > ~/.config/clamav/clamd.conf
- clamconf -g clamav-milter.conf > ~/.config/clamav/clamav-milter.conf
- touch /var/log/freshclam.log
- chmod 600 /var/log/freshclam.log
- chown clamav /var/log/freshclam.log

### Configuration (needed)
- vim Freshclam.conf
    - Uncomment line starting with UpdateLogFile, and change dir to /var/log/clamav/freshclam.log
- vim clamd.conf, and uncomment line starting with Example.

### Scan
- freshclam # Daemon might be running (systemctl stop/start, etc.)
- clamdscan --log=~/.config/clamav/logs/$(date).log /mnt/Storage

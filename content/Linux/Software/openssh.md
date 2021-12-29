### Hardening (see also: fail2ban)
- sudov /etc/ssh/sshd_config
- PermitRootLogin no

### Logs
- sudo tail -n 50 /var/log/auth.log

### Basic Local SSH (BAD--but handy for throw away local VMs)
- ssh -p 22 user@192.168.254.x
- <Enter Password>
- apt-get/dnf install sshpass
- sshpass -p your_password ssh user@192.168.254.x
- Script it
    - gpg --full-generate-key
    - mkdir $HOME/.passcrypt
    - vim ssh (create password file)
    - gpg --encrypt $HOME/.passcrypt/ssh.gpg
    - sshpassw="$(gpg -d $HOME/.passcrypt/ssh.gpg |)"
    - sshpass -p $sshpassw ssh user@192.168.254.x
- Also see: fail2ban && iptables

### Copy Files
- From Remote to local
    - scp username@b:/path/to/file /path/to/destination
- From local to remote
    - scp /path/to/file username@b:/path/to/destination

### Copy Directories
- scp -prq username@host:/path/to/file/ /path/to/destination/
- scp -prq /path/to/file/ username@host:/path/to/destination/

### Run X Programs on remote
- Setup
    - export DISPLAY:=0
- Send keyboard keys to GUI apps
    - xdotool key --window "$(xdotool search --class mpv)" p

### Mount Filesystems from remote
- mkdir /mnt/destination
- sshfs user@host:/source /mnt/destination
- cd /mnt/destination

### Mount Filesystems to remote
- mkdir /mnt/destination
- sshfs /source user@host:/destination
- cd /mnt/destination

### Fish Network Protocol
- Dolphin File Browser: fish://user@xxx.xxx.xxx
- MC: cd sh://user@xxx.xxx.xxx

### Passwordless login
- ssh-keygen -t rsa -b 4096 -C "your_email@domain.com" #username@reminder.com
    - Press enter for all entries
- ssh-copy-ide remote@remotesystem

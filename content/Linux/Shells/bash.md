### Symlink to /bin/sh
- sudo ln -sf bash /bin/sh

### Auto Completion
- Debian / Ubuntu
    - sudo apt-get install bash-completion
    - vim ~/.bashrc
    - ++ source /etc/profile.d/bash_completion.sh
- Arch
    - sudo pacman -S bash-completion
    - vim ~/.bashrc
    - ++ source /usr/share/bash-completion/bash_completion

### Arguments on the command line
- $@ == All user issued args
- $# == Number of args
- $0 == First arg (script/program)
- ${10} == 9th arg (10+ requires brackets)
- $1 == Second arg (user defined arg e.g. --help)
- $! == Process id of last command
- $? == Exit status id of last command
- $\*== All user issued args double quoted

### Bash Error Codes
- Package
    - moreutils
- errno errorcode

### Output to clipboard
- | xclip -selection c

### Resources
- https://tiswww.case.edu/php/chet/bash/bashref.html #wget http:// ...

### Add Pause to bashrc
- ++ # Enable pause
- ++ # Uses: pause;command
- ++ function pause(){
- ++    echo "Press [Enter] to continue...";grep $1 2>/dev/null;read
- ++ }

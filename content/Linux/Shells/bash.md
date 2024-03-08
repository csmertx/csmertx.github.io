---
title: 💻 Bash
author: csmertx
date: February 3, 2023
weight: -20
---

<br />

> If you want scripts that are works of art check out Stack Overflow.

## Symlink to /bin/sh

- ```sudo ln -sf bash /bin/sh```

## Auto Completion

- Debian / Ubuntu

    - ```sudo apt-get install bash-completion```

    - ```vim ~/.bashrc```
    
        ```
        ++ source /etc/profile.d/bash_completion.sh
        ```

- Arch

    - ```sudo pacman -S bash-completion```
    
    - ```vim ~/.bashrc```

        ```
        ++ source /usr/share/bash-completion/bash_completion
        ```

## Arguments on the command line

- ```$@``` All user issued args

- ```$#``` Number of args

- ```$0``` First arg (script/program)

- ```${10}``` 9th arg (10+ requires brackets)

- ```$1``` Second arg (user defined arg e.g. --help)

- ```$!``` Process id of last command

- ```$?``` Exit status id of last command

- ```$*``` All user issued args double quoted

## Bash Error Codes

- Package

    - ```moreutils```

        > errno errorcodes

## Cloak output errors

- ```cat /box 2> /dev/null```

## Output to clipboard
- ```command | xclip -selection c```

## Add Pause to ~/.bashrc

```
# Enable pause
# Uses: pause;command
function pause(){
   echo "Press [Enter] to continue...";grep $1 2>/dev/null;read
}
```

- Example: ```pause; echo "Pause Complete"```

> I use this in conjunction with [Tmux](/Linux/Software/tmux) helper [Tmuxinator](https://github.com/tmuxinator/tmuxinator), so that STDOUT renders out everything correctly

## Resources

- [Bash Reference Manual](https://tiswww.case.edu/php/chet/bash/bashref.html)

- [GNU Bash](https://www.gnu.org/software/bash/)
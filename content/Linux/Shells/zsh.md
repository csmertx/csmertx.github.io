---
title: ZSH Shell
author: csmertx
date: February 3, 2023
weight: -20
---

### Add Pause to ~/.zshrc

```
# Enable pause
# Uses: pause;command
function pause(){
   echo "Press [Enter] to continue...";grep $1 2>/dev/null;read
}
```

- Example: ```pause; echo "Pause Complete"```

> I use this in conjunction with [Tmux](/Linux/Software/tmux) helper [Tmuxinator](https://github.com/tmuxinator/tmuxinator), so that STDOUT renders out everything correctly
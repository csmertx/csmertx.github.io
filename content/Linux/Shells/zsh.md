---
title: 💻 ZSH
author: Chris Schammert (csmertx -- Christopher Schammert)
published: 2023-02-03
weight: -20
---

<br />

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
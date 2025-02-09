---
title: 💻 ZSH
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-03
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

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

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Shells/zsh.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Shells \ ZSH">
       History 🕵️
    </a>
</div>
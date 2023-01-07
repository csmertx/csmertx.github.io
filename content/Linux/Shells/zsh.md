---
title: ZSH Shell
weight: -20
---

### Add Pause to zshrc
- ++ # Enable pause
- ++ # Uses: pause;command
- ++ function pause(){
- ++    echo "Press [Enter] to continue...";grep $1 2>/dev/null;read
- ++ }

---
title: Markdown CLI
author: csmertx
date: February 3, 2023
weight: -20
---

<br />

> Hacky way to preview Markdown via terminal emulator

## Setup to preview Markdown via Lynx CLI browser

- Add ```~/.local/bin``` to ```$PATH```

- ```vim ~/.profile```

    ```
    if [ -d "$HOME/.local/bin" ] ; then
        PATH="$HOME/.local/bin:$PATH"
    fi
    ```


- vim ~/.local/bin/rmd

    ```
    #!/bin/bash
    pandoc $1 --highlight-style=zenburn \
    | sed \"1s/^/<html> \n</title>rmd<\/title>/" \
    | sed '$s/$/\n<\/html>/' | lynx -stdin
    ```

- ```w3m``` doesn't like stdin, but ```elinks``` (without -stdin) works

## Open via Ranger File Manger

- ```Ranger```

    - Navigate to ```file.md```

    - ```:open_with rmd```

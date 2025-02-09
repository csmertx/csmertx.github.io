---
title: 💻 Markdown CLI
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-03
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

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

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Software/markdown_cli.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Software \ Markdown CLI">
       History 🕵️
    </a>
</div>
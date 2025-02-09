---
title: 💻 Rsync
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-04
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Dry Run

- ```rsync --dry-run```

## Copy Directory to Remote

- ```rsync -avzh source/ user@host:/destination```

## Copy Directory to Remote w/SSH

- ```rsync -avzhe ssh /destination user@host:/source```

## Copy from remote

- ```rsync -avzh user@host:/source /destination```

## Copy From remote w/SSH

- ```rsync -avzhe ssh user@host:/source /destination```

## Resources

- [Rsync Homepage](https://rsync.samba.org/)

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Software/rsync.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Software \ Rsync">
       History 🕵️
    </a>
</div>
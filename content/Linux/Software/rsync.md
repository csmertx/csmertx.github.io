---
title: 💻 Rsync
author: Chris Schammert (csmertx -- Christopher Schammert)
published: 2023-02-04
weight: -20
---

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
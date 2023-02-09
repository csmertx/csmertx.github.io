---
title: Rsync
author: csmertx
date: February 4, 2023
weight: -20
---

# Rsync: Open source utility for incremental file transfer

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
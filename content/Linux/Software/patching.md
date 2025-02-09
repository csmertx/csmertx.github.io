---
title: 💻 Patching C Code
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-04
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

> For when someone says, "Patch your systems people!"

## Create a patch

- ```diff -u original/code.c modified/code.c > code.patch```

## Test Before Applying

- ```patch --dry-run```

## Apply a patch

- ```patch -u original/code.c modified/code.c -i codes.patch```

## Apply Patch and backup original

- ```patch -u -b original/code.c modified/code.c -i code.patch```

## Create a patch of a directory

- ```diff -ruN original/ modified/ > code.patch```

## Apply a patch of a directory

- ```patch -ruN -d working < slang.patch```

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Software/patching.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Software \ Patching C Code">
       History 🕵️
    </a>
</div>
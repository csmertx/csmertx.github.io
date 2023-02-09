---
title: Patch C
author: csmertx
date: February 4, 2023
weight: -20
---

# Applying patches to C source code

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


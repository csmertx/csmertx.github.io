---
title: 💻 Awk
author: csmertx
date: January 31, 2023
weight: -20
---

<br />

> Make selections, and do stuff with those selections

## Print Nth item in row

- ```hostname -i | awk '{print $1}'```

## Pull info out of quotes

- ```echo "\<a href="www.duckduckgo.com"\>" | awk -F '"' '{print $1}'```

## Resources

- [The GNU Awk User's Guide](https://www.gnu.org/software/gawk/manual/gawk.html)

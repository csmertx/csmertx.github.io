---
title: 💻 Awk
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-01-31
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

> Make selections, and do stuff with those selections

## Print Nth item in row

- ```hostname -i | awk '{print $1}'```

## Pull info out of quotes

- ```echo "\<a href="www.duckduckgo.com"\>" | awk -F '"' '{print $1}'```

## Resources

- [The GNU Awk User's Guide](https://www.gnu.org/software/gawk/manual/gawk.html)

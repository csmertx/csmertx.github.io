---
title: AWK
weight: -20
---

### Print Nth item in row
- hostname -i | awk '{print $1}'

### Pull info out of quotes
- echo "\<a href="www.duckduckgo.com"\>" | awk -F '"' '{print $1}'

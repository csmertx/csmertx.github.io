---
title: Grep
author: csmertx
date: January 31, 2023
weight: -20
---

## Find match or match

- ```grep 'match\|match2'```

- ```grep -E 'match|match2'```

## Find match and match

- ```grep 'match.*match2'```

## Omit match

- ```grep -v 'match'```

## Find first or last of line match

- ```grep "^match"```

- ```grep "match$"```

## Resources

- [GNU Grep](https://www.gnu.org/software/grep/)
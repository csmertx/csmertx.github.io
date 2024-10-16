---
title: 💻 Grep
author: Chris Schammert (csmertx)
published: 2023-01-30
weight: -20
---

<br />

## Recursive matching

> Recursive: check subdirectories

- ```grep -r term4search /dir```

## Exclude Match

- ```grep -v term2exclude /dir/file```

## Match and match

- ```egrep -w 'term1|term2' /dir/file```

## Ignore case

- ```grep -i searchterm /dir/file```

## String multiple matches

- ```grep -e term1 -e term2 -e term3 /dir/file```

## Search via extensions

> .txt, .mp3, .svg, .sh, .bash, .conf, etc.

- ```grep -e term1 -e term2 /dir/*.txt```

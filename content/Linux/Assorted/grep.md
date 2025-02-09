---
title: 💻 Grep
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-01-30
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

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

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 01/07/2023 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Assorted/grep.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Assorted \ Grep">
       History 🕵️
    </a>
</div>

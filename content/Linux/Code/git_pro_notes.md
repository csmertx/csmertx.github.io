---
title: 💻 Git Pro Notes
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-01-31
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

> Notes from before 2022

> Git Pro was written by Ben Straub, and Published by Apress

## Print tags

- ```git tag```

## Extended info

- ```git show v1.4```

## Adding tags to older commits (parse first)

- ```git log --pretty=oneline```

    > example output: 9fceb02... updated rakefile

## Append the tag

> to: ```[updated rakefile] commit```

- ```git tag -a v1.2 9fceb02```

## Sharing tags

- ```git push origin v1.5```

## All the tags all at once

- ```git push origin --tags```

## Even more info

- ```git checkout 2.0.0```

    > Read PG. 59 if needed... 

## Resources

- [Git Pro: book](https://git-scm.com/book/en/v2)

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/19/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Code/git_pro_notes.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Code \ Git Pro Notes">
       History 🕵️
    </a>
</div>
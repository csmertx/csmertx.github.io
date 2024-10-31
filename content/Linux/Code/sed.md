---
title: 💻 Sed
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-01-31
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Wrap every line output in quotes

- ```sed 's/"\(.*\)/"\1"/g'```


## Remove Whitespace Lines

- ```sed '/^$/d'```


## Remove everything before match

- ```sed 's/.*match//'```


## Remove everything after match

- ```sed 's/match.*//g'```


## Replace first instance of match

- ```sed '0,/example1/{s/example1/example2/}'```


## Replace Nth instance of match

- ```sed 's/example1/example2/2g```

    > 2g == 2nd match


## Print Nth Line

- ```sed -n '7p'```

    > 7th line


- ```sed '7!d'```

    > Also 7th line


## Replace newline chracter w/space

- Tip: Easier with ```tr```

    - ```tr '"\n' ' ' < input_filename```


## Remove brackets and everything inside brackets

- ```sed -e 's/\[[^][]*\]//g'```

## Add line numbers to the beginning of each line

- ```s/^/\=line('.').". "```

    - 🔗[Vim](/Linux/Software/vim): ```%s/^/\=line('.').". "```


## Resources

- [sed, a stream editor](https://www.gnu.org/software/sed/manual/sed.html)

- [Linux Handbook: Getting Stared With SED](https://linuxhandbook.com/sed-command-basics/)

- [linuxhint: 50 sed Command Examples](https://linuxhint.com/50_sed_command_examples)

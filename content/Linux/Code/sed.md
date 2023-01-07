---
title: Sed Command
weight: -20
---

#### Note: \* are escaped because markdown..

### Wrap every line output in quotes
- sed 's/"\(.*\)/"\1"/g'

### Remove Whitespace Lines
- sed '/^$/d'

### Remove everything before match
- sed 's/."\*match//'

### Remove everything after match
- sed 's/match."\*//g'

### Replace first instance of match
- sed '0,/example1/{s/example1/example2/}'

### Replace Nth instance of match
- sed 's/example1/example2/2g
- 2g == 2nd match

### Print Nth Line
- sed -n '7p' # 7th line
- sed '7!d' # Also 7th line

### Replace newline chracter w/space
- Tip: don't use sed...
- tr '"\n' ' ' < input_filename

### Remove brackets and everything inside brackets
- sed -e 's/"\[[^][]"*\]//g'

### Resources
- https://linuxhint.com/50_sed_command_examples

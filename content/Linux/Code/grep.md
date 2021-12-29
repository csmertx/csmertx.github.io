#### Note \* Astrisks are escaped because markdown

### Match or match
- grep 'match\|match2'
- grep -E 'match|match2'

### Match and match
- grep 'match.\*match2'

### Omit match
- grep -v 'match'

### Beginning/end of line match
- grep "^match"
- grep "match$"

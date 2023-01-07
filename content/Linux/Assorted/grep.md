---
title: Grep Command
weight: -20
---

### Recursive matching
- grep -r term4search /dir

### Exclude Match
- grep -v term2exclude /dir/file

### Match and match
egrep -w 'term1|term2' /dir/file

### Ignore case
- grep -i searchterm /dir/file

### String multiple matches
- grep -e term1 -e term2 -e term3 /dir/file

### Stick to .extension
- grep -e term1 -e term2 /dir/(asterisk).txt

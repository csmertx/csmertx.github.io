## Print tags
=> git tag

### Extended info
=> git show v1.4

### Adding tags to older commits (parse first)
=> git log --pretty=oneline  
example output: 9fceb02... updated rakefile

### Append the tag to <updated rakefile> commit
=> git tag -a v1.2 9fceb02

### Sharing tags
=> git push origin v1.5

### All the tags all at once
=> git push origin --tags

### Even more info
=> git checkout 2.0.0

### Read PG. 59 if needed... 
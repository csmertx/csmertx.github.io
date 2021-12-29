### Setup
- Add ~/.local/bin to $PATH
- vim ~/.local/bin/rmd
- ```++ #!/bin/bash```
- ```++```
- ```++ pandoc $1 --highlight-style=zenburn \```
- ```++ | sed \"1s/^/<html> \n</title>rmd<\/title>/" \```
- ```++ | sed '$s/$/\n<\/html>/' | lynx -stdin```
- w3m doesn't like stdin, but elinks (without -stdin) works

### Run
- w/Ranger
- :open\_with rmd

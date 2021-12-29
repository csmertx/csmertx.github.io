### Print subdirs or files in a dir
- cd $targetdir && find . -maxdepth 1 -mindepth 1 -type d -printf "%f"

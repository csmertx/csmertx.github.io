---
title: FFmpeg
weight: -20
---

### Combine files from a list
- cd to folder and open with ranger
- press v key and issue command :bulkrename
- in vim :w ~/Downloads/bulk.txt & exit
- bulkrename filenames in bulk.txt to: file 'constantpartoffilename_1.mp4'
- vim ~/Downloads/bulk.txt
- :%s/constantpartoffilename/file 'constantpartoffilename/g
- :%s/.mp4/.mp4'/g
- should result in: file 'constantpartoffilename_x.mp4'

### Editing
- Cut front beginning and end
    - ffmpeg -i "song.m4a" -ss 00:00:38 -t 00:04:16 "song.mp3"

### Compress phone videos for web/email (upload in minutes instead of hours)
ffmpeg -i input.mp4 -vcodec libx265 -crf 28 output.mp4

### Gif with subtitles (so-so quality)
![Gifski](https://gif.ski/) may be the right choice for high quality gifs, but here are the basics with FFmpeg.

Extract the subtitles if the subtitles are embeded (in this instance Scrubs Season 6 DVDs via MakeMKV).
```
ffmpeg -i "/home/chris/Downloads/Shares/dr_rad_got_the_hose.mkv" -map 0:s:0 "dr_rad_got_the_hose.srt"
```
Convert .mp4 to .gif while including subtitles and without changing the framerate (30fps).
```
ffmpeg -i "/home/chris/Downloads/Shares/dr_rad_got_the_hose.mkv" -vf subtitles="/home/chris/Downloads/Shares/dr_rad_got_the_hose.srt" "/home/chris/Downloads/Shares/dr_rad_got_the_hose.gif"
```

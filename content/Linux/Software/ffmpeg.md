---
title: FFmpeg
author: csmertx
date: February 3, 2023
weight: -20
---

## Combine files from a list (Ranger File Manager)

- cd to folder and open with ranger

- press ```v``` key and issue command ```:bulkrename```

- in vim ```:w ~/Downloads/bulk.txt``` & exit

- bulkrename filenames in bulk.txt to: file ```constantpartoffilename_1.mp4```

- ```vim ~/Downloads/bulk.txt```

    - ```:%s/constantpartoffilename/file 'constantpartoffilename/g```

    - ```:%s/.mp4/.mp4'/g```

- Should result in: file ```constantpartoffilename_x.mp4```


## Editing
Cut out a slice (audio)

```ffmpeg -i "song.m4a" -ss 00:00:38 -t 00:04:16 "song.mp3"```

### Cut out a slice (video)

```ffmpeg -i "2022-10-20 (1).mkv" -ss 00:00:00 -to 00:00:26 -c copy "2022-10-20 (1.1) - Snapping fingers (Character).mkv"```


### Compress phone videos for web/email (upload in minutes instead of hours)

```ffmpeg -i input.mp4 -vcodec libx265 -crf 28 output.mp4```


## Gif with subtitles (so-so quality)

- [Gifski](https://gif.ski/) may be the right choice for high quality gifs, but here are the basics with FFmpeg.

- Extract the subtitles if the subtitles are embeded (in this instance Scrubs Season 6 DVDs via MakeMKV).

    > Would not work via my copies of The Office DVD box sets, but that's ok.

- ```ffmpeg -i "/home/chris/Downloads/Shares/dr_rad_got_the_hose.mkv" -map 0:s:0 "dr_rad_got_the_hose.```srt"

- Convert ```.mp4``` to ```.gif``` while including subtitles and without changing the framerate (30fps).


    ```
    ffmpeg -i "/home/chris/Downloads/Shares/dr_rad_got_the_hose.mkv" -vf subtitles="/home/chris/Downloads/Shares/dr_rad_got_the_hose.srt" "/home/chris/Downloads/Shares/dr_rad_got_the_hose.gif"
    ```
<br />

<div style="text-align: center;">
<img src="https://i.imgur.com/Ydz5yKx.gif"/>

> Subtitles extracted from dr_rad_got_the_hose.mkv added to new dr_rad_got_the_hose.gif
</div>


## Changing subtitle font size and color for gifs/video

```
ffmpeg -i "/home/chris/Downloads/Shares/dr_rad_got_the_hose.mkv" -vf subtitles="/home/chris/Downloads/Shares/dr_rad_got_the_hose.srt:force_style='Fontsize=40,PrimaryColour=&H0000ff&'" "/home/chris/Downloads/Shares/dr_rad_got_the_hose.gif"
```
<br />

<div style="text-align: center;">
<img src="https://i.imgur.com/AlNT7JK.gif"/>

> Font size: 40pts, Color: H0000FF
</div>


## Changing (or adding) subtitle font background

```
ffmpeg -i "/home/chris/Downloads/Shares/dr_rad_got_the_hose.mkv" -vf subtitles="/home/chris/Downloads/Shares/dr_rad_got_the_hose.srt:force_style='Fontsize=40,PrimaryColour=&HFFFFFF&,OutlineColour=&H80000000,BorderStyle=3,Outline=0,Shadow=0,MarginV=20'" "/home/chris/Downloads/Shares/dr_rad_got_the_hose2.gif
```
<br />

<div style="text-align: center;">
<img src="https://i.imgur.com/hJU2r9r.gif"/>

> Background color: H0000000
</div>


## Resources

- [Stackoverflow: How to Add Font size in subtitles in ffmpeg video filter](https://stackoverflow.com/questions/21363334/how-to-add-font-size-in-subtitles-in-ffmpeg-video-filter)

- [SubStation Alpha](https://fileformats.fandom.com/wiki/SubStation_Alpha#Fields)

- [How to set background to subtitle in ffmpeg?](https://stackoverflow.com/questions/25870169/how-to-set-background-to-subtitle-in-ffmpeg)
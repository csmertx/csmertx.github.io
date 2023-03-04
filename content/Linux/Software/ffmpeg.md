---
title: FFmpeg
author: csmertx
date: February 28, 2023
weight: -20
---

<br />

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


## GIF with subtitles (so-so quality)

- [Gifski](https://gif.ski/) may be the right choice for high quality gifs, but here are the basics with FFmpeg.

- Extract the subtitles if the subtitles are embeded (in this instance Scrubs Season 6 DVDs via MakeMKV).

    > Would not work via my copies of The Office DVD box sets, but that's ok.

- ```ffmpeg -i "/home/chris/Downloads/Shares/dr_rad_got_the_hose.mkv" -map 0:s:0 "dr_rad_got_the_hose.srt"```

- Convert ```.mp4``` to ```.gif``` while including subtitles and without changing the framerate (30fps).


    ```
    ffmpeg -i "/home/chris/Downloads/Shares/dr_rad_got_the_hose.mkv" -vf subtitles="/home/chris/Downloads/Shares/dr_rad_got_the_hose.srt" "/home/chris/Downloads/Shares/dr_rad_got_the_hose.gif"
    ```
<br />

<div style="text-align: center;">
<img src="https://i.imgur.com/Ydz5yKx.gif"/>

> Subtitles extracted from dr_rad_got_the_hose.mkv added to new dr_rad_got_the_hose.gif
</div>

## GIF via PNG (pretty decent quality)

```
ffmpeg -i "/mnt/Storage/Videos/Movies/Ice Age 3: Dawn of the Dinosaurs (2009).mp4" -ss 00:34:18 -to 00:34:26 -c copy "/mnt/Storage/Videos/iceage3weasel/Ice_Age_3_weasel.mp4"
```

```ffmpeg -i "/mnt/Storage/Videos/iceage3weasel/Ice_Age_3_weasel.mp4" -vf fps=24 %d.png```
    
> For frame rate via Dolphin File Manager: Right click the file > Properties > Details > Frame Rate (23.98fps)

```cd /mnt/Storage/Videos/iceage3weasel/```

```ffmpeg -i %d.png iceage3weasel.gif```

### Could find no file with path '%d.png' and index in the range 0-4

```ffmpeg -start_number 54 -i %d.png iceage3weasel.gif```
> ```54``` in this case was the first image number

<div style="text-align: center;">
<img src="https://i.imgur.com/7UXtSnZ.gif"/>

> [Ice Age 3: Dawn of the Dinosaurs (character: Buck)](https://www.imdb.com/title/tt1080016/characters/nm0670408?ref_=tt_cl_c_18) via DVD rip
</div>

> Why not use .gifv or .webm? Video does not appear to be compatible with Github pages

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

## "Subtitle encoding currently only possible from text to text"

> Meaning the video is probably encoded with [PGS subtitles, which are image based subs, ](https://handbrake.fr/docs/en/latest/advanced/subtitles.html) and not text based.

### Subtitle Edit (GUI app)

- [Subtitle Edit: Dependencies](https://www.nikse.dk/subtitleedit/help#linux)

    - ```apti mono-complete```

    - ```apti libhunspell-dev```

    - ```apti libmpv-dev```

    - ```apti tesseract-ocr```

    - ```apti vlc```

    - ```apti ffmpeg```

- [Subtitle Edit: Download](https://github.com/SubtitleEdit/subtitleedit/releases/tag/3.6.11)

    - The Linux version is the first 'portable' option under ```Files```.

        > Please see the known issues: [Subtitle Edit for Linux](https://www.nikse.dk/subtitleedit/help#linux)

- Open Subtitle Edit with: ```mono SubtitleEdit.exe```

    > File > Open > Personal Files > ... (takes a little while to process)

    - Follow these [instructions](https://www.nikse.dk/subtitleedit/help#importvobsub) to use the GUI to convert subtitles using OCR.

- Desktop entry: ```vim /home/user/.local/share/applications/subtitleedit.desktop```

    ```
    [Desktop Entry]
    Comment[en_US]=Subtitle Edit
    Comment=Edit video subtitles
    Exec=mono /home/user/.sources/SubtitleEdit3611/SubtitleEdit.exe
    GenericName[en_US]=Subtitle Edit
    GenericName=Subtitle Edit
    Icon=/home/user/Pictures/Icons/subtitleedit.png
    Name[en_US]=Subtitle Edit
    Name=Subtitle Edit
    StartupNotify=true
    Terminal=false
    Type=Application
    Categories=AudioVideo;AudioVideoEditing;Audio;
    ```

    > SE Icon can be found [here](https://github.com/SubtitleEdit/subtitleedit/issues/675) or [here](https://user-images.githubusercontent.com/20923700/107876340-10da6a80-6ece-11eb-91e0-05902a474ac9.png).

    - ```sudo chmod +x /home/user/.local/share/applications/subtitleedit.desktop```

#### After converting the PGS to SRT

- ```ffmpeg -i "source_video.mkv" -vf "subtitleedit_converted.srt" "output_video_ready_for_memes.mp4"```

    > Future clips copied out of output_video.mp4 will contain subtitles for the scene

    > This method burns the subtitles to the video, so change font size, etc. if needed

<br />
<div style="text-align: center;">
<img src="https://i.imgur.com/9fSbHlW.gif"/>

> The City of Violence (2006) -- PGS to SRT
</div>
<br />

## Resources

- [Stackoverflow: How to Add Font size in subtitles in ffmpeg video filter](https://stackoverflow.com/questions/21363334/how-to-add-font-size-in-subtitles-in-ffmpeg-video-filter)

- [SubStation Alpha](https://fileformats.fandom.com/wiki/SubStation_Alpha#Fields)

- [How to set background to subtitle in ffmpeg?](https://stackoverflow.com/questions/25870169/how-to-set-background-to-subtitle-in-ffmpeg)

- [Stack Overflow: ffmpeg extract hdmv pgs subtitles from mkv to srt](https://stackoverflow.com/questions/62976902/ffmpeg-extract-hdmv-pgs-subtitles-from-mkv-to-srt)
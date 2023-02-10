---
title: YouTube-DL
author: csmertx
date: February 4, 2023
weight: -20
---

> See also [GitHub - yt-dlp/yt-dlp: A youtube-dl fork with additional features and fixes](https://github.com/yt-dlp/yt-dlp) 

## Auto Convert to mp3

- ```youtube-dl -x --audio-format mp3 http://videourl```

## Cron for "Podcast" mp3s

```
youtube-dl -x --audio-format mp3 --download-archive /my/video/path/downloaded.txt --no-post-overwrites --continue --no-overwrites --ignore-errors -o '/my/video/path/%(uploader_id)s/%(upload_date)s-%(title)s-%(id)s.%(ext)s' https://www.youtube.com/user/insertyourfavoriteyoutubeuserhere
```

## Video Playlist (Captain Scarlet and the Mysterons)
```
youtube-dl "https://www.youtube.com/watch?v=iDlFqC-FGWQ&list=PLm5cEiYdCR-fq23tVFa1ypzdt3Ya5DvB-" -o "%(title)s-.$(ext)s" --playlist-start 1 -f 18
```

## MP3 from Playlist

> Issue with %(ext)s 06-29-2020?
```
youtube-dl "https://www.youtube.com/watch?v=_DFypFVnSS0&list=PL_rR2s4GqBlaoriE6n0AvLGu_3e0_nHgr" -x --audio-format mp3 -o "%(title)s-.%(ext)s" --playlist-start 1
```

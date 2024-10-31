---
title: 💻 YouTube-DL
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2024-04-20
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

> See also [GitHub - yt-dlp/yt-dlp: A youtube-dl fork with additional features and fixes](https://github.com/yt-dlp/yt-dlp "Github.com | yt-dlp / yt-dlp")

> Linux Mint yt-dlp download: [yt-dlp via PyPi installation](https://github.com/yt-dlp/yt-dlp/wiki/Installation#with-pip "Github.com | yt-dlp / yt-dlp / Wiki / Installation w/PyPi")

> Kubuntu: [yt-dlp via binary software package](https://github.com/yt-dlp/yt-dlp/wiki/Installation#using-the-release-binary "Github.com | yt-dlp / yt-dlp / Wiki / Installation w/Release Binary")

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

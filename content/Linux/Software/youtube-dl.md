---
title: 💻 YouTube-DL
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2024-04-20
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Linux Mint & Ubuntu Install

1. ```sudo add-apt-repository ppa:tomtomtom/yt-dlp```

2. ```sudo apt update```

3. ```apti yt-dlp```

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

## Resources

- [GitHub - yt-dlp/yt-dlp: A youtube-dl fork with additional features and fixes](https://github.com/yt-dlp/yt-dlp "Github.com | yt-dlp / yt-dlp")

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Software/youtube-dl.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Software \ Youtube-DL">
       History 🕵️
    </a>
</div>
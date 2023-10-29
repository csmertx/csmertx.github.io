---
title: Hugo
author: csmertx
date: March 4, 2023
weight: -20
---

<br />

## Google Search Console verification (URL prefix) and Github Pages

- First step is to visit: 🔗 https://search.google.com/search-console?action=inspect

- Add downloaded ```googleXXXX.html``` to ```/static```

- Wait 3-5 minutes for Github Pages to update the site before clicking verify

- Add website sitemap via: 🔗 https://search.google.com/search-console/sitemaps
    
    > Hugo via Github Pages: ...user.github.io/sitemap.xml

- All that's left to do is wait in line for the site to be indexed

## Robots.txt blocking Google crawl

> [🔗 Google Search Console](https://search.google.com/search-console) > Indexing > Pages > Why pages aren’t indexed

> For me it was this URL: ...user.github.io/tags/

- ```vim ../config.toml```

    - Change ```enableRobotsTXT = true``` to ```enableRobotsTXT = false```

- Upload the following robots.txt to ```/static/robots.txt```

    ```
    User-agent: *
    Disallow:
    ```

## Geekdoc theme icons

- [🔗 Geekdocs.de | Build-in icons](https://geekdocs.de/features/icon-sets/#build-in-icons)

## Resources

- [🔗 Hugo: The world’s fastest framework for building websites](https://gohugo.io/)

- [🔗 Hugo Support: How to verify Hugo site to Google Search Console?](https://discourse.gohugo.io/t/how-to-verify-hugo-site-to-google-search-console/15078)

- [🔗 Search Facts: How to Use Robots.txt to Allow or Disallow Everything](https://searchfacts.com/robots-txt-allow-disallow-all/)

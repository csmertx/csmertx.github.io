---
title: 🏄 Hugo
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-03-04
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Google Search Console verification (URL prefix) and Github Pages

> 🔗[Namecheap Advanced DNS instructions](https://www.namecheap.com/support/knowledgebase/article.aspx/9252/2208/how-do-i-add-my-domain-to-google-sites/ "Namecheap.com | How do I add my domain to Google Sites")

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

- [🔗 Hugo | The world’s fastest framework for building websites](https://gohugo.io/)

- [🔗 Hugo Support | How to verify Hugo site to Google Search Console?](https://discourse.gohugo.io/t/how-to-verify-hugo-site-to-google-search-console/15078)

- [🔗 Search Facts | How to Use Robots.txt to Allow or Disallow Everything](https://searchfacts.com/robots-txt-allow-disallow-all/)

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 03/03/2023 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Web/hugo.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Web \ Hugo">
       History 🕵️
    </a>
</div>

---
title: 💻 Perl Language
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-01-31
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Print Nth instance of match

- ```perl -lne 'print $1 if /Today:(.*)/' < downloaded_webpage.txt```

    > Download webpage BEFORE scraping e.g. ```wget https://website.com/website.html > website.txt```

    > Or: ```TEMP="$(wget -q -O- "http://w1.weather.gov/xml/current_obs/stationcode.xml" | perl ...)"```

## Resources

- [Perl Programming Language Documentation](https://www.perl.org/docs.html)

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 01/07/2023 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Code/perl.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Code \ Perl Language">
       History 🕵️
    </a>
</div>

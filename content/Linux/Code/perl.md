---
title: Perl Language
author: csmertx
date: January 31, 2023
weight: -20
---

<br />

## Print Nth instance of match

- ```perl -lne 'print $1 if /Today:(.*)/' < downloaded_webpage.txt```

    > Download webpage BEFORE scraping e.g. ```wget https://website.com/website.html > website.txt```

    > Or: ```TEMP="$(wget -q -O- "http://w1.weather.gov/xml/current_obs/stationcode.xml" | perl ...)"```

## Resources

- [Perl Programming Language Documentation](https://www.perl.org/docs.html)

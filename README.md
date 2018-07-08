# Google News RSS as OPML

[Apparently](https://www.blog.google/products/news/new-google-news-ai-meets-human-intelligence/), Google has discontinued _Google News & Weather_. Instead there's only the _Google News_ app, which had _Google Play Newsstand_ merged in, with the interface more akin to the latter.

There could be an easy fix, since the _News & Weather_ interface was basically that of any RSS reader: access the topics, locations, and search queries of interest as RSS feeds. However, during the change, the [RSS subscription buttons were also dropped](https://www.seroundtable.com/google-news-rss-feed-gone-25795.html) from the _Google News_ website. This would still not be a problem, if their URLs were still correct. However, the naming scheme was changed as well and the old feeds show "This RSS feed URL is deprecated" messages ([among other problems](https://www.seroundtable.com/google-news-rss-feeds-deprecated-24717.html)).

This script tries to provide a workaround by generating an [OPML](https://en.wikipedia.org/wiki/OPML) file that should be importable by any* RSS reader with the current URLs (found by trial and error). It allows to customize topics, locations, and search queries as well as edition/country and language settings via a straight-forward commandline interface:

```
usage: gnrss2opml.py [-h] [-o OUTPUT] [-c COUNTRY] [-l LANGUAGE]
                     [-t [TOPIC [TOPIC ...]]] [-g [LOCATION [LOCATION ...]]]
                     [-q [QUERY [QUERY ...]]]

optional arguments:
  -h, --help            show this help message and exit
  -o OUTPUT, --output OUTPUT
                        output file name
  -c COUNTRY, --country COUNTRY
                        country / Google News edition (default: us)
  -l LANGUAGE, --language LANGUAGE
                        language (default: en)
  -t [TOPIC [TOPIC ...]], --topics [TOPIC [TOPIC ...]]
                        list of topics, will be converted to uppercase
                        (default: WORLD NATION BUSINESS TECHNOLOGY
                        ENTERTAINMENT SPORTS SCIENCE HEALTH)
  -g [LOCATION [LOCATION ...]], --locations [LOCATION [LOCATION ...]]
                        list of geographic locations (default: None)
  -q [QUERY [QUERY ...]], --queries [QUERY [QUERY ...]]
                        list of search queries (default: None)
```

*So far this has been tested with [Flym](https://f-droid.org/packages/net.frju.flym) and [Feeder](https://f-droid.org/packages/com.nononsenseapps.feeder). Both are open source and available in [f-droid](https://f-droid.org).


# gofeed

**NOT FINISHED YET**

Gofeed was inspired by feed43.com. It is useful to extract feeds from the website who does not provide one. Gofeed can even parse several websites into one full-text feed. 

This simple program was written when I started to learn golang. So I tried to reinvent everything I used including a simple crawler which took good use of cache and a very simple rss2.0 feed generator.

## Features

* Like feed43.com, you can extract feed titles, feed links and the feed descriptions with the following predefined patterns. Note that all these patterns are lazy and perform leftmost match, which means they will match as few characters as possible.
    *  {any}: match any character including newline
    *  {title}: title of feed entry, matched against the Feed.URL page
    *  {link}: hyper link of feed entry, matched against the Feed.URL page
    *  {description}: full-text description of feed entry, matched against the corresponding {link} page
* The crawler knows well when to request new html and when to use local html cache. This will save a lot of bandwidth.
* Several websites in one full-text feed.
 
## Things need to be improved

*  The crawler only understands tcp protocol.
*  Lacking URL normalization.
*  Little documentation.

## More functions on the todo list

1. <del>Cache old requests: use sqlite to cache downloaded web pages and save their lastmod time.</del>
2. Add alternative methods to extract feed title, link and description from html
    1. xpath

## Install

Firstly, you should install the sqlite driver `go-sqlite3`.

    go get github.com/mattn/go-sqlite3

Then install gofeed.

    go get github.com/mawenbao/gofeed

## Configuration example

See `example_config.json`.

## License

BSD license, see LICENSE.txt for more details.


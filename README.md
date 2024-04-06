# invision-scraper

A bash script for scraping invision forums in json.

## Requirements

 - [hgrep](https://github.com/TUVIMEN/hgrep)
 - [jq](https://github.com/stedolan/jq)

## Installation
    
    install -m 755 invision-scraper /usr/bin

## Supported links formats

    http(s)?://forum.com/topic/.*
    http(s)?://forum.com/forum(s)?/topic/.*
    http(s)?://forum.com/forums/.*
    http(s)?://forum.com/forum(s)?/forums/.*
    http(s)?://forum.com/.*/forums/.*
    http(s)?://forum.com.*


## Json format

Here's example of [topic](topic-example.json), and [user](user-example.json).

## Supported forums examples
    
    https://invisioncommunity.com/forums/
    https://linustechtips.com/
    https://www.thehuntinglife.com/forums/
    https://forum.htc.com/

## Usage

    invision-scraper [URL]...

Script downloads pages of threads and users and writes them in files. Files are named by their id's, but user files start with 'm-'.

Download forum into current directory using 4 processes

    invision-scraper -p 4 'https://forum.com/forums/19-name/'

Download thread by irregular thread url into DIR 

    invision-scraper -d DIR -t 'https://forum.com/abcdef/loop/'

Download forum quicker by ignoring user profiles and reactions

    invision-scraper -N -n -c 'https://forum.com/forums/82-jus/'

Download whole forum

    invision-scraper -c 'https://forum.com/forums/'

Get some help

    invision-scraper -h

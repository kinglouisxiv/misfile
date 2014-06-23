# misfile #

Source files for an [Index](http://www.louisxiv.co.uk/misfile/) to the [Misfile](http://www.misfile.com/) webcomic.

The index page is generated from two files: _index.txt_ and _tags.txt_. 

index.txt is the main list of comic pages and relevant tags -- characters and significant items. 

tags.txt has shortish explanation of the tags, where it is not glaring obvious from context.

Processing of the files through a python script [cig.py](https://github.com/kinglouisxiv/cig)  allows simple markup through [Markdown](http://daringfireball.net/projects/markdown/syntax) and embedded html.

index.txt
---------

lines with leading ; are for comments, not processed.

Each page is described by a set of key:value pairs

Key	| Use
-----	|----
page:	| comic page ID, heads a comic page entry. The Misfile page date. 
desc:	| a description of the page's story
note:	| other, non-story text, links 
tag:	| a tag for the page's story: a character, item, location, etc.
url:	| the actual comic page url

**Suggestion**: page: should be left-aligned, other keys should have leading whitespace to clearly show their subordinate relationship to the preceding page: key.

desc: and note: are processed for Markdown formatting

example index page entry:

```
page:2013-07-24
	url: http://www.misfile.com/?date={0}
	tag: ch-19
	tag: Emily
	tag: McArthurRes
	tag: MsMcArthur
	desc: I let you be friends with that Ash girl, but you need to broaden your horizons.
	note: mention of the Rich Bitch squad: [Jenny Greene](#jennygreene), Abigail LaFontain, Brittany Wu
```

url: http://www.misfile.com/?date={0} substitutes pageid value for {0} giving a valid link

tags.txt
--------

The tags definition file is: 

- comments, marked by leading semicolon ";"
- tag & definition pairs, tab separated

**tag** as above: a tag should be valid as an html class. Last definition wins

**Processing**: definition text is processed for simple Markdown formatting & links, and html passthrough. Tags starting "ch-" are treated as chapter markers.

example tag entry: 

```
Emily	Emily McArthur, “Blues”; our other protagonist; drives a [Nissan 240SX](#nissan240sx) and classic [Mustang](#mustang)
```


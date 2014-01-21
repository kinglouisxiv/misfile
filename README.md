# misfile #


Support files for an [Index](http://www.louisxiv.co.uk/misfile/) to the [Misfile](http://www.misfile.com/) webcomic

**Nota Bene**: This is very much a test of githubbing, at the moment.

The index page is generated from two files: _index.txt_ and _tags.txt_. 

index.txt is the main list of comic pages and relevant tags -- characters and significant items. 

tags.txt has shortish explanation of the tags, where it is not glaring obvious from context. 

Both files use leading ";" for comments and tabs to separate fields. Processing of the files  allows simple markup through [Markdown](http://daringfireball.net/projects/markdown/syntax) and embedded html can be used for what Markdown can't achieve here -- mostly embedded linebreaks with \<br\>.

## index.txt

Example:

_to follow_

Format:

Lines starting with a semi-colon ; are assumed to be comments and ignored, otherwise:

```
pageid	tag1	tag2	...	tagN	#comment
```

The separators are tab characters, not spaces.

### pageid

There must be one of these.

The unique portion of the page url -- for Misfile this is the page date, _e.g._ 2014-01-21. 


### tags

There can be none, one or several to a page.

Generally: a character, item or location name visible in the page. Something of interest about the page, preferably that might occur elsewhere in the comic, though singleton points-of-interest are inevitable, such as named characters who only occur once. Sometimes a reference to something or someone not on-page is important enough to tag.

A tag _must_ be

- a valid as a css class name

 tag _should_ be

- shortish
- memorable
- easy to type
- consistent
- unique when folded to lowercase


### #comment

There must be a terminating # though there need not be a comment

**Bug**: don't follow the # with a tab.

The free-text field. Usually a starter or important line of dialog, or a description or comment. Something significant that may bring the page to a reader’s mind.

Where a page establishes a day or date and rates a **dates** tag, use a embedded html to pull out the reference, _e.g._

```
<span class="dt">2005-01-11 02:00 Tuesday</span><br>
``` 

or 

```
<span class="dt">Saturday</span><br>
``` 

and follow the \<br\> with the normal page comment/description.


## tags.txt

Example:

_to follow_

Format:

Lines starting with a semi-colon ; are assumed to be comments and ignored, otherwise:

```
tag	description
```

The separator is a tab character, not spaces.

A tag _must_ be

- valid as a css class name

A tag _should_ be

- shortish
- memorable
- easy to type
- consistent
- unique when folded to lowercase

To explain the last two: Due to the way tag processing is done "TAG", "TaG" and "tag" generate the same css class of "tag" but different entries in the tag list. This breaks  things. 



... _tbc_ ...

----


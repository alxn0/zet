# Basic markdown

Basic markdown is essentially the syntax defined by John Gruber in
2004 in collaboration with Aaron Swartz[^ref1], based on previous formating used in
emails and usenet[^ref2]. For what I know, it seems to be implemented in most flavors.

An introduction of the syntax and the complete specification can be
found on John Gruber web page[^ref3]

## Paragraphs

A paragraph are consecutive lines of text.  
Paragraphs are separated by one ore more blank lines.  

**Hard line breaks**: meaning a new sentence on a new line; is done by adding 2 or 
more spaces at the end of the previous line.

**New paragraph** are done by adding an empty lines in between two
paragraphs.

## Headers

Can be either in *Setext* (`==` and `--`) and *atx* format (one or multiple `#`).  
There's 2 levels of setext and 6 of atx.

```
# This is a first header in atx

This is a first header in Setext
=================================

## This is a second header in atx

And a second header in setext
-----------------------------

### ATX header may be (optionnaly) enclosed ###
```

## Emphasis

| Style                     | Syntax                 | Example                          | Output                        |
|---------------------------|------------------------|----------------------------------|-------------------------------|
| Bold                      | `** **` or `__ __`     | `I like **bold** __text__`       | I like **bold** **text**      |
| Italic                    | `* *` or `_ _`         | `I like *italic* _text_`         | I like *italic* *text*        |
| Bold and italic [^info1]  | `*** ***` or `___ ___` | `*** This is super important***` | ***This is super important*** |

## Blockquotes

Start line witn `>` followed by **space**.  
Blockquotes can included other 

```
Simple blockquote
> So, where’s the Cannes Film Festival being held this year?
Christina Aguilera

Multiple paragraphs quotes
> Dorothy followed her through many of the beautiful rooms in her castle.
>
> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.
Wizard of oz

Nested quotes
> Why quoting?
>> Because its fun!
```

## Horizontal rules

Use three or more hyphens `---`, asterisks `***`, or underscores `___`

## List

Unordered list start with `-`, `+`, or `*`
Ordered list start with numbers and followed by `.` or `)`

List can be nested with indentation

```
- Unordered Item
    1. Sub ordered item
    2. Another sub ordered items
- Second unordered items
```

## Links and images

Link use `[text](path)` while image use `![text](image path)`

## Code

Inline code are enclosed by single backticks `` ` `` [^info2].  

Code blocks are produced by indenting lines by at least 4 spaces or
a tab.

```
# Here some R code
some_data <- read.csv("./data.csv")
summary(some_data)
```

## Special characters

Escape special characters with `\`

Characters that can be escaped:

| Symbol | name             |
<https://daringfireball.net/projects/markdown/syntax#html>
|--------|------------------|
| \\     | backslase        |
| \`     | backtick         |
| \*     | asterisk         |
| \_     | underscore       |
| \{\}   | curly braces     |
| \[\]   | square brackets  |
| \(\)   | parentheses      |
| \#     | hash mark        |
| \+     | plus sign        |
| \-     | hyphen           |
| \.     | dot              |
| \!     | exclamation mark |

## Automatic links

Simply surroung URLs and email adressess with `< >`

```
<perdu.com>
<myself@somewhere.com>
```

## inline HTML

As markdown is designed to *write* in a web format, it is converted HTML language [^info3].
Consequently, we can use HTML tags within a `md` document to format
syntax that is not defined in markdown.

**Block-level tags**
Block-level HTML elements (e.g. `<div>`, `<table>`, `<p>`) must be separated from content by blank lines, 
and the start and end tags should not be indented with tabs or spaces. 

Markdown syntax **is not processed** and cannot be used within block-level
tags

**Span-level tags**

Span-level HTML tags (e.g. `<span>`, `<cite>`, or `<del>`) can be used anywhere, 
and even replace markdown syntax (e.g., `<img>` instead of `![image
name]` format).

Markdown syntax **is processed** and **can be used** within span-level tags

## Automatic escaping

In HTML, `<` are used to start tags and `&` to specify entities.

To avoid complicating things, `<` will be treated as `&lt;` and `&` as
`&amp;` automaticaly. 

Yet, `<` will be treated as it when begining html tags, and `&TAG;` generate the entities.

```
&copy; is a copyrights
<p> is a tag
```

[^ref1]: See Aaron Swartz [ATX formatting](http://www.aaronsw.com/2002/atx/intro)
[^ref2]: <https://en.wikipedia.org/wiki/Markdown#History>
[^ref3]: <https://daringfireball.net/projects/markdown/>
[^info1]: Not specified in Gruber 2004 specification, but often
    considered as part of the basic format.
[^info2]: To enclosed a backticks within inline code like in this
    sentence, you need 2 backticks separation.
[^info3]: Although some *flavors* can be now converted to format other
    than HTML

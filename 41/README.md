# Basic markdown cheatsheet

Basic markdown is essentially the syntax defined by John Gruber in 2004
[^ref1] which borrows from Aaron Swartz atx structured text format [^ref2]. 
For what I know, it seems to be implemented in most flavors.

## Paragraphs

A paragraph are consecutive lines of text.  
Paragraphs are separated by one ore more blank lines.  
Line breaks, meaning a sentence on a new line, is done by adding 2 or
more spaces at the end of the previous line.

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
Code blocks are enclose with 3 backticks, as in the example below.

```
# Here some R code
some_data <- read.csv("./data.csv")
summary(some_data)
```

## Special characters

Escape special characters with `\`

Characters that can be escaped:

| Symbol | name             |
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

[^ref1]: https://daringfireball.net/projects/markdown/basics
[^ref2]: http://www.aaronsw.com/2002/atx/intro
[^info1]: Not specified in Gruber 2004 specification
[^info2]: To enclosed a backticks within inline code like in this
    sentence, you need 2 backticks separation.

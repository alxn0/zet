# Basic markdown and CommonMark

## Content
1. [Preliminary](#preliminary)
1. [Lines and paragraphs](#lines-and-paragraphs)
1. [Headers](#headers)
1. [Styling text](#styling-text)
1. [Block quote](#block-quote)
1. [List](#list)
1. [Code block](#code-block)
1. [Link](#link)
1. [Image](#image)
1. [Html](#html)
1. [Horizontal lines](#horizontal-lines-or-thematic-breaks)
1. [Escaped characters](#escaped-characters)

## Preliminary
Basic markdown is essentially the syntax defined by John Gruber in
2004 in collaboration with Aaron Swartz, based on previous formating used in
emails and usenet[^ref1]. For what I know, it seems to be implemented in most flavors.

An introduction of the syntax and the complete specification can be
found on John Gruber web page[^ref2]

A problem with John Gruber's markdown is that it is at some point
ambiguous. In response, CommonMark is an attempt to provide a strict and
compatible scpecification of basic markdown with some extension[^ref3].

This note present basic markdown following CommonMark
specification. See
this [note](../42) for more detailed differences between Gruber's
markdown and commonmark.

## Paragraphs
A paragraph are consecutive lines of text.

To obtain a **new line** (i.e., *hard break*), we need to add **2 spaces
at the end of the line**. Alternatively, the two spaces can be replaced
by a **backslash `\` at the end of the line**.

To obtain a **new paragraph**, we add an empty line in between paragraphs.

**Example**  
*In this code example, white spaces are displayed by interpunct `·`*
```md
This·is·a·line.
This·is·not·a·new·line.··
This·is·a·new·line.\
This·is·another·new·line.

This·is·a·new·paragraph.
```

**Output**  
This is a line.
This is not a new line.  
This is a new line.\
This is another new line.

This is a new paragraph.

## Header
Can be either in *Setext* (`==` and `--`) and *atx* format (one or multiple `#`).
There's 2 levels of setext and 6 of atx.

| Level | ATX Syntax  | Setext Syntax                        |
|-------|-------------|--------------------------------------|
| 1     | `# H1`      | `First header` <br> `============`   |
| 2     | `## H2`     | `Second header` <br> `-------------` |
| 3     | `### H3`    |                                      |
| 4     | `#### H4`   |                                      |
| 5     | `##### H5`  |                                      |
| 6     | `###### H6` |                                      |


## Styling text

| Style           | Syntax                      | Example                                 | Output                                |
|-----------------|-----------------------------|-----------------------------------------|---------------------------------------|
| Bold            | `** **` or <br> `__ __`     | `This is **bold**`                      | This is **bold**                      |
| Italic          | `* *` or <br> `_ _`         | `This is _italic_`                      | This is *italic*                      |
| Nested emphasis | `* *` with <br> `_ _`       | `**This is bo ld with nested _italic_**` | **This is bold with nested _italic_** |
| Strong emphasis[^note1] | `*** ***` or <br> `___ ___` | `This is a ***strong emphasis***`       | This is a ***strong emphasis***       |
| Inline code[^note4]     | `` ` ` ``                   | `` This is a `function` ``              | This is a `function`                  |

## Block quote

Each line of a block quote begin with `>`. 
Blockquote can be nested.

**Example**
```md
> A quote from somebody
> That continue on a different line
>> With a nested quote
```

**Output**
> A quote from somebody
> That continue on a different line
>> With a nested quote

## List

| Style     | Syntax                                    | Example                                                                           |
| --------- | --------------------                      | --------------------------------------------------------------------------------- |
| Unordered | `-`, `+`, or `*`                          | <pre><code>- banana</code><br><code>- Apple</code><br><code>- Papaya</code></pre> |
| Ordered   | <code>1.</code> or <code>1)</code>        | <pre><code>1. Partridge</code><br><code>2. Turtle doves</code><br><code>3. French hens</code></pre> |
| Nested[^note2]    | Identing `ordered` and/or <br> `unordered`[^info2] | <pre><code>- banana </code><br><code>- Apple</code><br><code>  1. Gala</code><br><code>  2. McIntosh</code><br><code>- Papaya</code></pre>|

## Code block

**Indented code blocks**: Starting each lines with **4 spaces**.  
**Fenced code blocks**:  Enclosing sections with either three backticks <code>\`\`\`</code>
of three tilds ` ~~~ ` (i.e., fenced code blocks)[^info1].

**Output of a code block**
```
i = 1
while i < 6:
  print(i)
  i += 1
```

## Link

### Untitled

| Style     | Syntax                                  | Example                                                                                   | Output                                               |
|-----------|-----------------------------------------|-------------------------------------------------------------------------------------------|------------------------------------------------------|
| Inline    | `[name](path)`                          | `[Lost?](www.perdu.com)`                                                                  | [lost?](perdu.com)                                   |
| Reference | `[name](tag)` <br> ⋮ <br> `[tag]: path` | `See CommonMark [specs](CM_specs)` <br> ⋮ <br> `[cm_specs]: https://spec.commonmark.org/` | See CommonMark [specs](https://spec.commonmark.org/) |
| Autolinks | `<URL>` or `<email>`                    | `<https://theuselessweb.com/>`                                                            | <https://theuselessweb.com/>                         |

**Path** can be either a *URL*, an *email adress* or
a *relative path* on the hosted server.

### Titled

**Inline and reference links** can also come with an optionnal **title** which will be displayed when
hovering the hyperlink with a mouse. Simply add a `"title"` after the
`path`.

**Exemple**
```md
This **untitled** [link](https://www.pcjs.org/) point to an IBM PC emulator
for browser

This **titled** [link](https://onlinebakery.eu/ "Online bakery") let you
slice bread online
```

This **untitled** [link](https://www.pcjs.org/) point to an IBM PC emulator
for browser

This **titled** [link](https://onlinebakery.eu/ "Online bakery") let you
slice bread online

## Image

Like *standard links*, but with an `!` at the begining. They can have
optionnal *titles* as for links.

**Exemple**
```md
![box character](https://github.com/n48.png "Box character") 
```

**Output**

![box character](https://github.com/n48.png "Box character") 

## Inline html
As markdown is designed to *write* in a web format, it is converted HTML [^note3].
Consequently, we can use HTML tags to format output.

## Block-level tags

There must be **no empty-lines** within block-level HTML elements (e.g. `<div>`, `<table>`, `<p>`).

Markdown syntax **is not processed** and cannot be used within block-level
tags.

**Example**
```md
 <table>
  <tr>
    <th>column A </th>
    <th>column B</th>
    <th>column C</th>
  </tr>
  <tr>
    <td>foo</td>
    <td>bar</td>
    <td>baz</td>
  </tr>
  <tr>
    <td>qux</td>
    <td>corge</td>
    <td>thud</td>
  </tr>
</table>
```

**Output**
 <table>
  <tr>
    <th>column A </th>
    <th>column B</th>
    <th>column C</th>
  </tr>
  <tr>
    <td>foo</td>
    <td>bar</td>
    <td>baz</td>
  </tr>
  <tr>
    <td>qux</td>
    <td>corge</td>
    <td>thud</td>
  </tr>
</table>


## Span-level tage
Span-level HTML tags (e.g. `<span>`, `<cite>`, or `<del>`) can be used anywhere,
and even replace markdown syntax (e.g., `<img>` instead of `![image
name]` format).

Markdown syntax **is processed** and **can be used** within span-level tags

**Exemple**
```md
If <b>x = 2</b>, then <b>x<sup>2</sup>= 4</b>
This &copy; is a copyright logo
```

**Output**

If <b>x = 2</b>, then <b>x<sup>2</sup>= 4</b>  
This &copy; is a copyright logo

## Horizontal lines (or thematic breaks)

Simply use three or more hyphens (`---`), asteriks (`***`) or
underscores `___`. Note the characters can be *spaced*

**Example**
```md
---
* * *
```

**Output**
---
* * * 

## Escaped characters

### Backslash escape

All ASCII punctuations can be escaped with a precedding backslash `\`.
Escaped characters are treats.

```md
\!\"\#\$\%\&\'\(\)\*\+\,\-\.\/\:\;\<\=\>\?\@\[\\\]\^\_\`\{\|\}\~
```
ed as regular characters and do not have their usual Markdown meaning.  
Backslash before other characters are treated as usual basckslash.

### Automatic escaping
In HTML, `<` are used to start tags and `&` to specify entities.

To avoid complicating things, `<` will be treated as `&lt;` and `&` as
`&amp;` automaticaly.

Yet, `<` will be treated as it when begining html tags, and `&TAG;` generate the entities.

[^ref1]: <https://en.wikipedia.org/wiki/Markdown#History>
[^ref2]: <https://daringfireball.net/projects/markdown/>
[^ref3]: <https://commonmark.org/>
[^note1]: Only defined in CommonMark, not in Gruber's markdown.
[^note2]: Indentation for child-list must be at least to the first letter
    of the parent-list.
[^note3]: Although some flavors can be output to other format.
[^note4]: To display a backtick `` ` `` in inline-code, you need to
    enclose it within *pairs* of backticks (i.e., <code> `` ` ``
    </code>)



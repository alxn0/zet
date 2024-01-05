# Markdown cheatsheet

## Content
1. [Lines and paragraphs](#lines-and-paragraphs)
2. [Headers](#headers)
3. [Styling text](#styling-text)

## Lines and paragraphs
A simple *carriage return* at the end of the line will not be displayed in the html
output. To obtain a new line (i.e., hard break),  add **two spaces before at the end of the line**.

To obtains a **new paragraphs** add an **empty line** in between
paragraphs.

**Example**  
*In this code example, white spaces are displayed by star*
```
This*is*a*line.
This*is*not*a*new*line.**
This*is*a*new*line.

This*is*a*new*paragraph.
```

**Output**  
This is a line.
This is not a new line.  
This is a new line.

This is a new paragraph.

## Header

| Level | ATX Syntax  | Setext Syntax                        | Flavor |
|-------|-------------|--------------------------------------|--------|
| 1     | `# H1`      | `First header` <br> `============`   | B/C/G  |
| 2     | `## H2`     | `Second header` <br> `-------------` | B/C/G  |
| 3     | `### H3`    |                                      | B/C/G  |
| 4     | `#### H4`   |                                      | B/C/G  |
| 5     | `##### H5`  |                                      | B/C/G  |
| 6     | `###### H6` |                                      | B/C/G  |


## Styling text

| Style           | Syntax                      | Example                                 | Output                                | Flavor |
|-----------------|-----------------------------|-----------------------------------------|---------------------------------------|--------|
| Bold            | `** **` or <br> `__ __`     | `This is **bold**`                      | This is **bold**                      | B/C/G  |
| Italic          | `* *` or <br> `_ _`         | `This is _italic_`                      | This is *italic*                      | B/C/G  |
| Nested emphasis | `* *` with <br> `_ _`       | `**This is bold with nested _italic_**` | **This is bold with nested _italic_** | B/C/G  |
| Strong emphasis | `*** ***` or <br> `___ ___` | `This is a ***strong emphasis***`       | This is a ***strong emphasis***       | B/C/G  |
| Inline code     | `` ` ` ``                   | `` This is a `function` ``              | This is a `function`                  | B/C/G  |
| Strikethrough   | `~~ ~~`                     | `This is a ~~wrong~~`                   | This is a ~~wrong~~                   | G      |
| Math            | `$ $`                       | `$\sqrt{4} = 2$`                        | $\sqrt{4} = 2$                        | G      |
| Emoji           | `:EMOJICODE:`               | `:joy:`                                 | :joy:                                 | G      |

## Block quote

Each line of a block quote begin with `>`. 
Blockquote can be nested.

**Example**
```
> A quote from somebody
> That continue on a different line
>> With a nested quote
```

**Output**
> A quote from somebody
> That continue on a different line
>> With a nested quote

## Lists

| Style     | Syntax                                    | Example                                                                           |
| --------- | --------------------                      | --------------------------------------------------------------------------------- |
| Unordered | `-`, `+`, or `*`                          | <pre><code>- banana</code><br><code>- Apple</code><br><code>- Papaya</code></pre> |
| Ordered   | <code>1.</code> or <code>1)</code>        | <pre><code>1. Partridge</code><br><code>2. Turtle doves</code><br><code>3. French hens</code></pre> |
| Nested    | Identing `ordered` and/or <br> `unordered`[^info2] | <pre><code>- banana </code><br><code>- Apple</code><br><code>  1. Gala</code><br><code>  2. McIntosh</code><br><code>- Papaya</code></pre>|

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

## Links


| Style     | Syntax                                  | Example                                                                                   | Output                                               |
|-----------|-----------------------------------------|-------------------------------------------------------------------------------------------|------------------------------------------------------|
| Inline    | `[name](path)`                          | `[Lost?](www.perdu.com)`                                                                  | [lost?](perdu.com)                                   |
| Reference | `[name](tag)` <br> ⋮ <br> `[tag]: path` | `See CommonMark [specs](CM_specs)` <br> ⋮ <br> `[cm_specs]: https://spec.commonmark.org/` | See CommonMark [specs](https://spec.commonmark.org/) |
| Autolinks | `<URL>` or `<email>`                    | `<https://theuselessweb.com/>`                                                            | <https://theuselessweb.com/>                         |

**Path** can be either a *URL*, an *email adress* or
a *relative path* on the hosted server.

**Inline and reference links** can also come with an optionnal **title** which will be displayed when
hovering the hyperlink with a mouse. Simply add a `"title"` after the
`path`.

**Exemple**
```
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
```
![box character](https://github.com/n48.png "Box character") 
```

**Output**

![box character](https://github.com/n48.png "Box character") 

## Inline html

You can use raw HTML in markdown.

**Exemple**
```
If <b>x = 2 </b>, then <b> x<sup>2</sup> = 4</b>
This &copy; is a copyright logo
```

**Output**

If <b>x = 2 </b>, then <b> x<sup>2</sup> = 4</b>
This &copy; is a copyright logo

## Horizontal lines (or thematic breaks)

Simply use three or more hyphens (`---`), asteriks (`***`) or
underscores `___`. Note the characters can be *spaced*


<!--
Links can be eiter in the format `[Link](path)` or `[Link](tag)` with
later the reference to the tag `[tag]: path`

Path can be either a *relative path* within the server or a *URL*.  

**Exemple**  
```
See this [note](../43) on the difference between Grubers' markdown and CommonMark

Lost on the web? Go to [perdu.com](tag)

[tag]: perdu.com
```

**Output**  
See this [note](../43) on the difference between Grubers' markdown and CommonMark

Lost on the web? Go to [perdu.com](tag)

[tag]: perdu.com
-->


[^info1]: Fenced code blocks are not specified in Gruber's basic
    markdown syntax.
[^info2]: Child list must be indented at least to the first letter of
    the parent list.

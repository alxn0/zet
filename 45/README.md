# Markdown cheatsheet

## Header

| Level | ATX Syntax  | Setext Syntax                        | Flavor |
|-------|-------------|--------------------------------------|--------|
| 1     | `# H1`      | `First header` <br> `============`   | B/C/G  |
| 2     | `## H2`     | `Second header` <br> `-------------` | B/C/G  |
| 3     | `### H3`    |                                      | B/C/G  |
| 4     | `#### H4`   |                                      | B/C/G  |
| 5     | `##### H5`  |                                      | B/C/G  |
| 6     | `###### H6` |                                      | B/C/G  |


## Styling (inline) text

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
| Ordered   | <code>1.</code> or <code>1)</code>         | <pre><code>1. Partridge</code><br><code>2. Turtle doves</code><br><code>3. French hens</code></pre> |
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
| inline    | `[name](path)`                          | `[Lost?](www.perdu.com)`                                                                  | [lost?](perdu.com)                                   |
| Reference | `[name](tag)` <br> ⋮ <br> `[tag]: path` | `See CommonMark [specs](CM_specs)` <br> ⋮ <br> `[cm_specs]: https://spec.commonmark.org/` | See CommonMark [specs](https://spec.commonmark.org/) |
| Autolinks | `<URL>` or `<email>`                    | `<https://theuselessweb.com/>`                                                            | <https://theuselessweb.com/>                         |

**Note** that *path* can be either a *URL*, an *email adress* or
a *relative path* on the hosted server

## Image

Like *standard links*, but with an `!` at the begining

**Exemple**
```
![box character](https://github.com/n48.png) 
```

**Output**
![box character](https://github.com/n48.png) 

## Inline html

You can use raw HTML in markdown.

 <ul>list</ul>

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
<!--
| Syntax                | Or                  |  to Get               |
|-----------------------|-----------------------|-----------------------|
| \*Italic\*            | \_Italic\_            | *Italic*              |
| \*\*Bold\*\*          | \_\_Bold\_\_          | **Bold**              |
| \# Heading 1          | Heading 1\            | # Heading 1 {#h       |
|                       | =========             | eading-1 .smaller-h1} |
+-----------------------+-----------------------+-----------------------+
| \## Heading 2         | Heading 2\            | ## Heading 2 {#h      |
|                       | \-\-\-\-\-\-\-\--     | eading-2 .smaller-h2} |
+-----------------------+-----------------------+-----------------------+
| \                     | \[Link\]\[1\]\        | [Link](htt            |
| [Link\](http://a.com) | ⋮\                    | ps://commonmark.org/) |
|                       | \[1\]: http://b.org   |                       |
+-----------------------+-----------------------+-----------------------+
| !\[Imag               | !\[Image\]\[1\]\      | ![Markdown](images/fa |
| e\](http://url/a.png) | ⋮\                    | vicon.png){width="36" |
|                       | \[1\]:                | height="36"}          |
|                       | http://url/b.jpg      |                       |
+-----------------------+-----------------------+-----------------------+
| \> Blockquote         |                       | > Blockquote          |
+-----------------------+-----------------------+-----------------------+
| \* List\              | \- List\              | -   List              |
| \* List\              | - List\               | -   List              |
| \* List               | - List\               | -   List              |
+-----------------------+-----------------------+-----------------------+
| 1\. One\              | 1\) One\              | 1.  One               |
| 2. Two\               | 2) Two\               | 2.  Two               |
| 3. Three              | 3) Three              | 3.  Three             |
+-----------------------+-----------------------+-----------------------+
| Horizontal rule:\     | Horizontal rule:\     | Horizontal rule:      |
| \                     | \                     |                       |
| \-\--                 | \*\*\*                | -------------------   |
+-----------------------+-----------------------+-----------------------+
| \`Inline code\` with  |                       | `Inline               |
| backticks             |                       |  code`{.preformatted} |
|                       |                       | with backticks        |
+-----------------------+-----------------------+-----------------------+
| \`\`\`\               | [····]{.spaces}\#     | ::: code-block        |
| \# code block\        | code block\           | \# code block\        |
| print \'3 backticks   | [····]{.spaces}print  | print \'3 backticks   |
| or\'\                 | \'3 backticks or\'\   | or\'\                 |
| print \'indent 4      | [····]{.spaces}print  | print \'indent 4      |
| spaces\'\             | \'indent 4 spaces\'   | spaces\'              |
| \`\`\`                |                       | :::                   |
+-----------------------+-----------------------+-----------------------+

-->

...

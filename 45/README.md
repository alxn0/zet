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
| Strikethrough   | `~~ ~~`                     | `This is a ~~wrong~~`                   | This is a ~~wrong~~                   | B/C/G  |
| Inline code     | `` ` ` ``                   | `` This is a `function` ``              | This is a `function`                  | B/C/G  |
| Math            | `$ $`                       | `$\sqrt{4} = 2$`                        | $\sqrt{4} = 2$                       | G      |

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

Lists can be either **unordered** using `-`, `+` or `*` or **unordered**
using `1.` or `1)`.

List can also be **nested**; the **identation of the _child list_ must be at
least at the first letter of the _parent list_**.  

**Example**
```
1. Banana
2. Apple
  * Gala
  * McIntosh
3. Papaya
```

**Output**
1. Banana
2. Apple
   * Gala
   * McIntosh
3. Papaya

## Code block

Code on multiple lines can be either declared by starting lines with **4 spaces** (i.e., idented code blocks) 
or by enclosing sections with either three backticks <code>\`\`\`</code>
of three tilds ` ~~~ ` (i.e., fenced code blocks)[^info1].

**Example**
Indented code block
    a = b
    c = b
    a == c

Fenced code block
~~~
i = 1
while i < 6:
  print(i)
  i += 1
~~~

**Output**
```
Indented code block
    a = b
    c = b
    a == c

Fenced code block
~~~
i = 1
while i < 6:
  print(i)
  i += 1
~~~
```




## Mathematical expressions

## References


[^info1]: Fenced code blocks are not specified in Gruber's basic
    markdown syntax.
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

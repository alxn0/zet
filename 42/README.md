# Some specifications of commonMark 

CommonMark[^ref1] provides a strictly defined specification for Markdown syntax
that aims to resolve ambiguities and inconsistencies that existed in John
Gruber's original Markdown implementation[^ref2]. 

There is implementations of CommonMark in doznes of programming
language[^ref3] and various sites, mainly GitHub, GitLab and Stack
Exchange.

Some of the main differences or more strictly defined syntax include:

**ATX Headings**:
- *Gruber's markdown* allow zero, 1 or more spaces between the `#`
  and the header text
- *CommonMark* requires to be only 1 space after the `#`

**Emphasis and strong emphasis**:
In *CommonMark*:
- There is no intrawords emphasis with `_`
- Strong emphasis are defined by three `*` or `_` (i.e., bold and
  italic)
- Clear distinction between `*` and `_` which facilitate nested emphasis

```
this_is_not_emphasis_while_**this_is**
***Strong emphasis***
**Nested _emphasis_**
```

**Indented code blockes**:
- *Gruber's Markdown* allows for indented code blocks **at least 4 spaces or a tab**,
- *CommonMark* requires a code block to be indented by **exactly four spaces
or one tab**.

```
Text

    Indented code block
    with consistent indentation
```

**Fenced code blocks**: 
*CommonMark* provides a way to specify code blocks with
three backtick `` ` `` or tilde `~`

```
\`\`\` 
a = b
b = c
\`\`\`

```

**Lists**:
*Gruber's Markdown*: 
- lists can be somewhat ambiguous, especially for nested
  lists and the required indentation.

*CommonMark*:
- A list can interrupt a paragraph
- There can be one to 4 spaces between the list characters (e.g.,
  `-`) and the text[^info1].
- Requires that continuation lines in lists be aligned with the
  text of the list item they are a part of.
- Nested list need to be intended at least to the first character of
  the parent list

```
This is a some text
- List that interupt a paragraphe
-  New item with more identation, see that the
   continuation is aligne with the previous line.
   - Nested list
```

**Escaped characters**

Any ASCII punctuation may be backlashed escaped.

```
\!\"\#\$\%\&\'\(\)\*\+\,\-\.\/\:\;\<\=\>\?\@\[\\\]\^\_\`\{\|\}\~
```

**HTML blocks**

In some respect, CommonMark is less restrictive here.

*Gruber markdown*:

- HTML block need to be preceded by a blank line
- Does not allow the start tag to be indented
- requires a matching end tag, also not indented

*CommonMark*:

- HTML blocks continue until they are closed by their appropriate end condition, 
  or the last line of the document or other container block.
- **No blank line inside HTML block**

**Thematic Breaks**:
- *Gruber's Markdown*: Uses horizontal rules but may be inconsistent in
    parsing different formats.
- *CommonMark*: A line with three or more  `*` ,  `-` , or  `_`  characters, which
    can be separated by spaces but not by other characters, forms a thematic
    break.

```
Text above

***

Text below
```
[^ref1]: <https://commonmark.org/>
[^ref2]: <https://daringfireball.net/projects/markdown/syntax>
[^ref3]:
    <https://github.com/commonmark/commonmark-spec/wiki/List-of-CommonMark-Implementations>
[^ref4]: <https://spec.commonmark.org/>
[^info1]: More than 4 spaces will trigger an indented code block



# GitHub Flavored markdown and advanced formating

GitHub Flavored Markdown (GFM) is a strict superset of CommonMark, meanings it
only add features, but do not change what's specified in the
later[^ref1].

It worth noting that not everything is found in the GFM
specifications[^ref1][^note1], but are explained in the writting on Github
Guide[^ref2].

This is not an thorough guide, but note on what I use.

For more information, see GitHub writing and formating guide[^ref2]

**Footnotes**
Like *linked references*, but use the `[^ref]` syntax.

```
Some citation[^ref]

[^ref]: the complete references
```

Will put all references on the bottom of the page with a thematic
break, places according to citation order.

**Tables**
Tables are structured using pipes `|`, inline text and hyphen `-`.
The header, separator and content format look like this:

```
| foo | bar |
| --- | --- |
| baz | bim |
| taz | tim |

```

**Task list items**
Like a normal list, but with a `[ ]` separating the list character
(.e.g, `-`) and the inline text[^note2]. The left/right brakets can be
either separated by a whitespace or a x.

```
- [ ] TODO
- [x] DONE!
```

Worth noting that task list can be used to manage issue or pull
request[^ref5]

**Striketrough**
Strike items between a pairs of `~`

```
~~This is a mistake~~
```

**Extended autolinks**
Autolinks can be constructed without `<` and `>`, it will be recognized
with `www.` and a valid domain. Same for email and xmpp with `@` and valid
domain. More complex scheme of autolinks are found
[here](https://github.github.com/gfm/#autolinks-extension-)

**Disallowed HTML tags**
There tags are dissalowed for security reasons

    <title>
    <textarea>
    <style>
    <xmp>
    <iframe>
    <noembed>
    <noframes>
    <script>
    <plaintext>

**Emoji**
Add emojis by typing `:EMOJICODE:`.
See this
[cheatshee](https://github.com/ikatyang/emoji-cheat-sheet/blob/master/README.md)
for a complete list of emoji and code.

**Mathematical expressions**
Support the LaTeX math formating[^ref3] using MathJax implementation[^ref4].  
Inline expression are delimited with single `$`, and code expressions
are with double `$$`.

See this stackexchange
[post](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)
for quick reference on mathjax syntax

**Collapsed sections**

Collaps sections within the `<details>` tages, and provide information
with `<summary>`.

```
<details>

<summary> Collapse section</summary>

## Some header

Blablablablabla

</details>
```

**Highlights code blocks**

Fence code blocks on GitHub can be highlighted by an optionnal
language identifier (e.g., python) after the 3 `` ` `` or `~`

Here is some hightlighted R code.

```R
some_df <- read.csv("./some_data.csv")
lapply(some_df, class)
```

See
[here](https://github.com/github-linguist/linguist/blob/master/lib/linguist/languages.yml)
 for valid language

**Mermaid diagram**


***TODO***

- [x] Footnotes
- [x] Tables
- [x] Strikethroughs
- [x] Task list
- [x] Auto linked references
- [x] Emoji
- [ ] Mathematical expressions
- [ ] Collapsed sections
- [ ] Highlights code block
- [ ] Mermaid diagram

[^ref1]: <https://github.github.com/gfm/>
[^ref2]: <https://docs.github.com/en/get-started/writing-on-github>
[^ref3]: <https://en.wikibooks.org/wiki/LaTeX/Mathematics>
[^ref4]: <https://docs.mathjax.org/en/latest/input/tex/index.html#tex-and-latex-support>
[^ref5]:
    <https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/about-task-lists>
[^note1]: For example, there is a [discussion](https://github.com/orgs/community/discussions/44669)
          on missing specification on footnotes
[^note2]: They specified that `-` and `[ ]` can be separated by an
    optionnal number of spaces in the GFM specs. Still, it must be
    between 1 and 4, as more than four may triggered a code block

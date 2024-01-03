# Some specifications of commonMark 

- [ ] What is CommonMark
- [ ] Main differences from basic markdown
- [ ] GitHub Flavored Markdown as a strict superset

## CommonMark
CommonMark[^ref1] is an attempt to create a strongly defined and highly
compatible version of markdown.

It was developpend by a group of developper who wanted to create an
unambiguous specification of the language, as the original ambiguity of Gruber
specification[^ref2] generated multiple implementations, and mostly
confusion for the users. 

To address these inconsistencies, CommonMark was developed as a standard specification 
of Markdown that aimed to be compatible with Gruber's original 
vision, but also being unanbiguous so that behavior is predictable across different
platforms.

There is implementations of CommonMark in doznes of programming
language[^ref3] and various sites, mainly GitHub, GitLab and Stack
Exchange.

Still, the specification is *highly technical*, intended for
implementation, and is confusing for simple usage[^ref4].

Below are general definitions and some of the main differences between 
Gruber's original Markdown and CommonMark with syntax examples, trying to present
them in an understandable manner.

## Block and inlines

Apart from the notion of **characters** (i.e., Unicode Code poin) and **lines** 
(i.e., a sequence of zero or more characters), mardown document are
represented as a sequence of **blocks** with **inlines**.

**Blocks** represent the *structure* of the document, they can be seen
as a sequence of aggregated information.

Blocks are divided in:

1. **Container blocks**: Which can contains other blocks:
    - Lists (i.e., list of list)
    - List items
    - Block quotes
2. **Leaf blocks**: which contains inlines
    - Thematic breaks (i.e., horizontal lines)
    - Headings
    - Code blocks
    - Html blocks
    - Linked reference
    - Paragraphs
    - Blank lines

In comparison, **inline** contains *content*. They include:
- Code span
- Emphasis
- Links
- Images
- Autolinks
- Raw HTML
- Hard and soft line breaks
- Textual contents

From a user perspective, this conceptualization of markdown document does not change how we write
markdown, but help to think about the syntax *organizing* syntax into
broader categories.

Mostly, it help understand the following changes, as they are express in
those concepts.

## Blank Lines Before Blocks
In original Markdown, you could often start a block-level element immediately
after a paragraph, whereas CommonMark typically requires a blank line before
block-level elements like lists and code blocks.

**Gruber's Markdown Example**:
```
    Text
    - List item 1
    - List item 2
```

**CommonMark Example**:
```
    Text

    - List item 1
    - List item 2
```

## Indented Code Blocks:
Original Markdown allows for indented code blocks with less strict rules,
while CommonMark requires a code block to be indented by exactly four spaces
or one tab.
  
  - Gruber's Markdown: Code block beginning with at least 4 spaces or
    1 tab
  - CommonMark: Must have precisely four spaces or one tab.



[^ref1]: <https://commonmark.org/>
[^ref2]: <https://daringfireball.net/projects/markdown/syntax>
[^ref3]:
    <https://github.com/commonmark/commonmark-spec/wiki/List-of-CommonMark-Implementations>
[^ref4]: <https://spec.commonmark.org/>
<!--


2. Indented Code Blocks:
Original Markdown allows for indented code blocks with less strict rules,
while CommonMark requires a code block to be indented by exactly four spaces
or one tab.
  • Gruber's Markdown: Code block beginning with any number of spaces might
  work.
  • CommonMark: Must have precisely four spaces or one tab.
3. ATX Headers Without Closing Punctuation:
CommonMark allows ATX-style headers ( #  for headings) without closing  # ,
whereas the original Markdown does not define a strict rule here. You may
find inconsistent interpretations in various Markdown processors.
  • Gruber's Markdown: The closing  #  are optional, but not specified.
  • CommonMark Example:
    # Heading 1
    ## Heading 2 ##

Both of the above are considered valid in CommonMark.
4. Setext Headers:
Original Markdown’s Setext headers (underlined using  =  for h1 and  -  for
h2) must be preceded by a blank line in CommonMark.
  • Gruber's Markdown: May not require a blank line before Setext headers.
  • CommonMark: Requires a blank line.
5. Link Definitions:
In CommonMark, link definitions cannot interrupt a paragraph, while in
Gruber's Markdown, they might be allowed to.
  • Gruber's Markdown: Might allow the following:
    This is a paragraph with a [link][id].
    [id]: http://example.com "Title"

  • CommonMark: Requires the definition to be separate from the paragraph:
    This is a paragraph with a [link][id].

    [id]: http://example.com "Title"

6. Lazy Continuation Lines:
Gruber's Markdown allows list continuations with less indentation, whereas
CommonMark requires that continuation lines in lists be aligned with the
text of the list item they are a part of.
  • Gruber's Markdown Example:
    - List item
    continuation of list item without alignment

  • CommonMark Example:
    - List item
      continuation of list item must be aligned

7. HTML Blocks:
The rules for parsing inline HTML are loosely defined in Gruber's Markdown
but are more strict in CommonMark. CommonMark clearly specifies which HTML
tags start and end HTML blocks and considers the content inside as raw HTML.
  • Gruber's Markdown: May parse inline HTML differently across
  implementations.
  • CommonMark: Strict rules about which inline HTML is recognized.
8. Entities and Escapes:
The handling of backslash escapes and HTML entities is more predictable in
CommonMark, which provides clear rules for when these are recognized.
  • Gruber's Markdown: Might have more variable behavior.
  • CommonMark: Has strict rules for entity and escape processing.
9. Lists:
Differences in how lists are parsed and nested can be significant between
the original Markdown and CommonMark. For instance, the way list items are
nested and whether blank lines are required between items can vary.
  • Gruber's Markdown: Less strict, varying implementations.
  • CommonMark: More precise rules for list parsing.
10. Thematic Breaks:
Also known as horizontal rules, thematic breaks are more strictly defined in
CommonMark than in original Markdown, where various implementations might
have different standards for what constitutes a valid thematic break.
  • Gruber's Markdown: Varies between implementations.
  • CommonMark Example:
    ---
    ***
    ___



These differences illustrate the need that CommonMark addressed: to create a
consistent specification across different Markdown processors, making it
easier for users to predict how their Markdown files will be rendered. It's
important to note that not all implementations of Markdown adhere strictly
to the original specification or to CommonMark, so actual behavior can still
vary, especially in less popular or older Markdown processors.

-->

# Some specifications of commonMark and GitHub flavored markdown

- [ ] What is CommonMark
- [ ] GHF as a strict superset of commonmark
- [ ] Main differences

**Ressources**

<https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github>
<https://github.github.com/gfm/>

---

**Kind of technical and documentation is complicated**

Here's a summary/simplification by GPT-4 turbo

## Questions
"What are the main differences between basic markdown (as define by John Grueber) and commonmark markdown flavors. Provides a detailed list of the differences with markdown syntax example. Be thorough, but in the same time understandable by a human. Do not simply state the specifications."

## Answer
Markdown, originally created by John Gruber, is a markup language that
allows for easy-to-read and easy-to-write plain text format that is converted
into structurally valid HTML. However, as Markdown became popular, it was
interpreted and implemented differently by various applications and
services, leading to inconsistencies. To address these inconsistencies,
CommonMark was developed as a standard, unambiguous specification of
Markdown that aimed to be compatible with Gruber's original vision but also
clearly specified so that behavior is predictable across different
platforms.

Below are some of the main differences between original Markdown (as defined
by John Gruber) and CommonMark with syntax examples, making sure to present
them in an understandable manner:

1. Blank Lines Before Blocks:
In original Markdown, you could often start a block-level element immediately
after a paragraph, whereas CommonMark typically requires a blank line before
block-level elements like lists and code blocks.
  • Gruber's Markdown Example:
    Text
    - List item 1
    - List item 2

  • CommonMark Example:
    Text

    - List item 1
    - List item 2

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


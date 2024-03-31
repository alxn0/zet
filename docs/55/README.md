# What could be a simple implementation of autocomplete for Keg

The idea is to emulate obsidian/notion/roam/etc. function to quicly find
other notes when using wiki style link. When calling [[EXEMPLE]], an
overlay box appears and show options.

There is a discussion on stackexchange to use custom files with built-in
omnicomp[^1]

## Options

1. Create a new index files with alread created links, such as
   `[NAME](../1)`
    - *Problem*: we will see all `[]` and `(../number)` when searching
    - *facilities*: `changes.md` already have this information
2. Use existing nodes.tsv, only query titles, and generate the full
   links when invoking
   - *problem* can we send something else when autocompleting?

## Work with multiple keg
- It should find `nodes.tsv` or `changes.md` relative to the opened
  files (i.e., `../dex/.`)

[^1]:
    <https://vi.stackexchange.com/questions/4584/how-to-create-my-own-autocomplete-function>

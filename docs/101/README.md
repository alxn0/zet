# Vim: !COMMAND 

It is possible to execute shell command from within the editor.
It is a powerfull tool to automate stuff within VIM.

- `:COMMAND` execute COMMAND and display output in a extended
  command area
- `:.!COMMAND` replace the current line with the output of COMMAND
    - Can be called using `!!` in normal mode
- `%COMMAND` execute COMMAND and replace all the lines
    - `%` is a shortcut for range `1,$`
- `n,m!COMMAND` execute COMMAND on line `n,m`
- `r!COMMAND` insert the output of COMMAND on the line below
- `w!COMMAD` write the file to STDOUT which can be used as input for
  COMMAND
    - Particularly useful with to pass snippet of code through visual
      mode to shell function

**Notes** that `!` followed by nothis will execute last command

## References

<https://learnbyexample.github.io/tips/vim-tip-26/>

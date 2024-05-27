# Python pass vs continue

`continue`: Skip the current iteration of a loop and continue with the next iteration.
`pass`: Do nothing.

Why using `pass` ?
- To avoid getting an error when an empty code is not allowed.
- To avoid getting an error when a code is not implemented yet.

```python
try:
    1/0
except:
    pass
```

## References
<https://stackoverflow.com/questions/9483979/is-there-a-difference-between-pass-and-continue-in-a-for-loop-in-python#9484008>

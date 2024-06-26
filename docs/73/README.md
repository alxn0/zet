# Prompt engineering: Ask for structure output format

Use pre-specified output format to simplify answers, but can also be
injected as input for other functions (e.g. HTML, JSON, ASCII Table, 
mermaid graph)

## Exemple

```python
prompt = f"""
Generate a list of three made-up book titles along \ 
with their authors and genres. 
Provide them in JSON format with the following keys: 
book_id, title, author, genre.
"""
```

```python
response = get_completion(prompt)
print(response)
```

## References

[deeplearning.ai Prompt Engineering short course](https://learn.deeplearning.ai/courses/chatgpt-prompt-eng)



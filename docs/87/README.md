# LLM Coding: Simplify code

- Ask the LLM to perform a code review.
- Note that adding/removing newline characters may affect the LLM completion that gets output by the LLM.

## Option 1: Detailed process explanation
```python
prompt_template = """
Can you please simplify this code for a linked list in Python?

{question}

Explain in detail what you did to modify it, and why.
"""
```

## Option 2: with expert and code comment
```python
# option 2
prompt_template = """
Can you please simplify this code for a linked list in Python? \n
You are an expert in Pythonic code.

{question}

Please comment each line in detail, \n
and explain in detail what you did to modify it, and why.
"""
```



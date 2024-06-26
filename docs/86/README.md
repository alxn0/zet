# LLM Coding: Improving existing code

- An LLM can help you rewrite your code in the way that's recommended for that particular language.
- You can ask an LLM to rewrite your Python code in a way that is more 'Pythonic".

### Single solution

```python
prompt_template = """
I don't think this code is the best way to do it in Python, can you help me?

{code}

Please explain, in detail, what you did to improve it.
"""
```

### Ask for multiple ways of rewriting your code

```python
prompt_template = """
I don't think this code is the best way to do it in Python, can you help me?

{code}

Please explore multiple ways of solving the problem, and explain each.
"""
```

## References
From [deeplearning.ai short course on pair programmine with LLM](https://learn.deeplearning.ai/pair-programming-llm)


# LLM coding: Make code more efficient


- Improve runtime by potentially avoiding inefficient methods (such as ones that use recursion when not needed).
- The LLM is neutral and not invested in particular algorithm, can spark ideas / inspiration on what can be done instead.

```python
prompt_template = """
Can you please make this code more efficient?

{question}

Explain in detail what you changed and why.
"""
```

## References
From [deeplearning.ai short course on pair programmine with LLM](https://learn.deeplearning.ai/pair-programming-llm)


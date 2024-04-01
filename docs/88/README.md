# LLM coding: Write test cases

- It may help to specify that you want the LLM to output "in code" 
to encourage it to write unit tests instead of just returning test cases in English.

```python
prompt_template = """
Can you please create test cases in code for this Python code?

{code}

Explain in detail what these test cases are designed to achieve.
"""
```

## References
From [deeplearning.ai short course on pair programmine with LLM](https://learn.deeplearning.ai/pair-programming-llm)


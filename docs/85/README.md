# LLM: Pair Programmning Scenarios

Some exemple of LLM application to coding

- Scenario 1: [Improve existing code](../86)
- Scenario 2: [Simplify code](../87)
- Scenario 3: [Write test cases](../88)
- Scenario 3: [Make code more efficient](../89)

### Scenario 4: Make code more efficient

- Improve runtime by potentially avoiding inefficient methods (such as ones that use recursion when not needed).
- The LLM is neutral and not invested in particular algorithm, can spark ideas / inspiration on what can be done instead.

```python
prompt_template = """
Can you please make this code more efficient?

{question}

Explain in detail what you changed and why.
"""
```

### Scenario 5: Debug your code

```python
prompt_template = """
Can you please help me to debug this code?

{question}

Explain in detail what you found and why it was a bug.
"""
```

### Scenario 6: Explain complex code

```python
prompt_template = """
Can you please explain how this code works?

{question}

Use a lot of detail and make it as clear as possible.
"""
```

### Scenario 7: Write documentation

```python
prompt_template = """
Please write technical documentation for this code and \n
make it easy for a non swift developer to understand:

{question}

Output the results in markdown
"""
```

## References
From [deeplearning.ai short course on pair programmine with LLM](https://learn.deeplearning.ai/pair-programming-llm)

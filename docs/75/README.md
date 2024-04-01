# Prompt engineering tactic: Few-shot prompting

- Give succescul examples of completing tasks. Then ask the model to
  perform the task
- Work like a mini training.
- E.g., start a discussion between an expert and a beginner
to provide context on the way we want the LLM to answer

## Exemple
```python
prompt = f"""
Your task is to answer in a consistent style.

<child>: Teach me about patience.

<grandparent>: The river that carves the deepest \ 
valley flows from a modest spring; the \ 
grandest symphony originates from a single note; \ 
the most intricate tapestry begins with a solitary thread.

<child>: Teach me about resilience.
"""
```

```python
response = get_completion(prompt)
print(response)
```

## References
[deeplearning.ai Prompt Engineering short course](https://learn.deeplearning.ai/courses/chatgpt-prompt-eng)

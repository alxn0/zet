# Using a String Template

Summarize multiple strategies in a single template.

## Prompt template
1. priming: getting the LLM ready for the type of task you'll ask it to do.
    - What can of expert?
    - In what style?
    - [Few-shot prompting](../75)
2. question: the specific task.
3. decorator: how to provide or format the output.
    - [Specific format (e.g., md, json)](../73)
    - [Steps for task completion](../76)
    - [Work its own solution](../77)


```python
prompt_template = """
{priming}

{question}

{decorator}

Your solution:
"""
```

## Priming and question

```python
priming_text = "You are an expert at writing clear, concise, Python code."

question = "create a doubly linked list"
```

## Observe how the decorator affects the output

- In other non-coding prompt engineering tasks, it's common to use 
"chain-of-thought prompting" by asking the model to work through 
the task "step by step".

- For certain tasks like generating code, you may want to experiment 
with other wording that would make sense if you were asking a 
developer the same question.

### Option 1
```python
decorator = "Work through it step by step, and show your work. One step per line."
```

### Option 2
```python
decorator = "Insert comments for each line of code."
```

## Applications
- Ollama Modelfile[^1]

## References
From [deeplearning.ai short course on pair programming with a LLM](https://learn.deeplearning.ai/courses/pair-programming-llm)
[^1]: <https://ollama.com/hub/modelfiles>

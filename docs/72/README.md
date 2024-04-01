# Prompt engineering: use delimiters

The idea is to pinpoint important element within the prompt

- e.g, triple quotes / backtics / dashes, angle brackets, XML tags
- Using delimeters allows to limit prompt injection when 
  building an application. 
- If the sentence "forget the previous instruction" is 
within delimeters for example used to
circoncise text to summarize, it will not be interpreted as
an instruction per se.

## Exemple
```python
text = f"""
You should express what you want a model to do by \ 
providing instructions that are as clear and \ 
specific as you can possibly make them. \ 
This will guide the model towards the desired output, \ 
and reduce the chances of receiving irrelevant \ 
or incorrect responses. Don't confuse writing a \ 
clear prompt with writing a short prompt. \ 
In many cases, longer prompts provide more clarity \ 
and context for the model, which can lead to \ 
more detailed and relevant outputs.
"""
```

```python
prompt = f"""
Summarize the text delimited by square brackets \ 
into a single sentence.
<{text}>
"""
response = get_completion(prompt)
print(response)
```

## References

[deeplearning.ai Prompt Engineering short course](https://learn.deeplearning.ai/courses/chatgpt-prompt-eng)


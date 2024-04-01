# PE: Summarize

Exemple with a toy product review

## Text to summarize

```python
prod_review = """
Got this panda plush toy for my daughter's birthday, \
who loves it and takes it everywhere. It's soft and \ 
super cute, and its face has a friendly look. It's \ 
a bit small for what I paid though. I think there \ 
might be other options that are bigger for the \ 
same price. It arrived a day earlier than expected, \ 
so I got to play with it myself before I gave it \ 
to her.
"""
```

## Summarize with a word/sentence/character limit

```python
prompt = f"""
Your task is to generate a short summary of a product \
review from an ecommerce site. 

Summarize the review below, delimited by triple 
backticks, in at most 30 words. 

Review: \`\`\`{prod_review}\`\`\`
"""

response = get_completion(prompt)
print(response)
```

## Summarize with a focus on shipping and delivery
```python
prompt = f"""
Your task is to generate a short summary of a product \
review from an ecommerce site to give feedback to the \
Shipping deparmtment. 

Summarize the review below, delimited by triple 
backticks, in at most 30 words, and focusing on any aspects \
that mention shipping and delivery of the product. 

Review: \`\`\`{prod_review}\`\`\`
"""

response = get_completion(prompt)
print(response)
```

>**Comment**
> - Summaries include topics that are not related to the topic of focus.

## Try "extract" instead of "summarize"

```python
prompt = f"""
Your task is to extract relevant information from \ 
a product review from an ecommerce site to give \
feedback to the Shipping department. 

From the review below, delimited by triple quotes \
extract the information relevant to shipping and \ 
delivery. Limit to 30 words. 

Review: \`\`\`{prod_review}\`\`\`
"""

response = get_completion(prompt)
print(response)
```

## References
[deeplearning.ai Prompt Engineering short course](https://learn.deeplearning.ai/courses/chatgpt-prompt-eng)

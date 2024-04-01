# Principles of Prompting

## Principle 1: Write **clear**[^1] and **specific** instructions


- Tactic 1: [Use delimiters](../72)

### Tactic 1: Use delimiters
- e.g, triple quotes / backtics / dashes, angle brackets, XML tags
- Using delimeters allows to limit prompt injection when 
  building an application. 
    - If the sentence "forget the previous instruction" is 
    within delimeters for example used to
    circoncise text to summarize, it will not be interpreted as
    an instruction per se.

```python
text = "SOME TEXT" 

prompt = f"""
Summarize the text delimited by square brackets \ 
into a single sentence.
<{text}>
"""
```

### Tactic 2: Ask for structure output format
- E.g. HTML, JSON, ASCII Table, mermaid graph

```python
prompt = f"""
Generate a list of three made-up book titles along \ 
with their authors and genres. 
Provide them in JSON format with the following keys: 
book_id, title, author, genre.
"""
```

### Tactic 3: Check whether conditions are satisfied
- Check assumpptions required to do the task.
- Ask to rephrase the questions as STEPS

```python
text = f"""
Making a cup of tea is easy! First, you need to get some \ 
water boiling. While that's happening, \ 
grab a cup and put a tea bag in it. Once the water is \ 
hot enough, just pour it over the tea bag. \ 
Let it sit for a bit so the tea can steep. After a \ 
few minutes, take out the tea bag. If you \ 
like, you can add some sugar or milk to taste. \ 
And that's it! You've got yourself a delicious \ 
cup of tea to enjoy.
"""
prompt = f"""
You will be provided with text delimited by triple quotes. 
If it contains a sequence of instructions, \ 
re-write those instructions in the following format:

Step 1 - ...
Step 2 - …
…
Step N - …

If the text does not contain a sequence of instructions, \ 
then simply write \"No steps provided.\"

\"\"\"{text}\"\"\"
"""
```

###  Tactic 4: Few-shot prompting
- Give succescul examples of completing tasks. Then ask the model to
  perform the task
- Work like a mini training.
- E.g., start a discussion between an expert and a beginner
to provide context on the way we want the LLM to answer

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
response = get_completion(prompt)
print(response)
```

### Principle 2:  Give the model time to think

#### Tactic 1: Provide the steps for task completion

```python
text = f"""
In a charming village, siblings Jack and Jill set out on \ 
a quest to fetch water from a hilltop \ 
well. As they climbed, singing joyfully, misfortune \ 
struck—Jack tripped on a stone and tumbled \ 
down the hill, with Jill following suit. \ 
Though slightly battered, the pair returned home to \ 
comforting embraces. Despite the mishap, \ 
their adventurous spirits remained undimmed, and they \ 
continued exploring with delight.
"""
```

**Example 1**

```python
prompt_1 = f"""
Perform the following actions: 
1 - Summarize the following text delimited by triple \
backticks with 1 sentence.
2 - Translate the summary into French.
3 - List each name in the French summary.
4 - Output a json object that contains the following \
keys: french_summary, num_names.

Separate your answers with line breaks.

Text:
<{text}>
"""
response = get_completion(prompt_1)
print("Completion for prompt 1:")
print(response)
```

**Exmaple 2**

```python
prompt_2 = f"""
Your task is to perform the following actions: 
1 - Summarize the following text delimited by 
  <> with 1 sentence.
2 - Translate the summary into French.
3 - List each name in the French summary.
4 - Output a json object that contains the 
  following keys: french_summary, num_names.

Use the following format:
Text: <text to summarize>
Summary: <summary>
Translation: <summary translation>
Names: <list of names in summary>
Output JSON: <json with summary and num_names>

Text: <{text}>
"""
response = get_completion(prompt_2)
print("\nCompletion for prompt 2:")
print(response)
```

#### Tactic 2: Instuct the model to work out its own solution
- Simple instruction: Work your own solution and report each steps

```python
prompt = f"""
Your task is to determine if the student's solution \
is correct or not.
To solve the problem do the following:
- First, work out your own solution to the problem including the final total. 
- Then compare your solution to the student's solution \ 
and evaluate if the student's solution is correct or not. 
Don't decide if the student's solution is correct until 
you have done the problem yourself.

Use the following format:
Question:
---
question here
---
Student's solution:
---
student's solution here
---
Actual solution:
---
steps to work out the solution and your solution here
---
Is the student's solution the same as actual solution \
just calculated:
---
yes or no
---
Student grade:
---
correct or incorrect
---

Question:
---
I'm building a solar power installation and I need help \
working out the financials. 
- Land costs $100 / square foot
- I can buy solar panels for $250 / square foot
- I negotiated a contract for maintenance that will cost \
me a flat $100k per year, and an additional $10 / square \
foot
What is the total cost for the first year of operations \
as a function of the number of square feet.
--- 
Student's solution:
---
Let x be the size of the installation in square feet.
Costs:
1. Land cost: 100x
2. Solar panel cost: 250x
3. Maintenance cost: 100,000 + 100x
Total cost: 100x + 250x + 100,000 + 100x = 450x + 100,000
---
Actual solution:
"""
response = get_completion(prompt)
print(response)
```

## References
[deeplearning.ai Prompt Engineering short course](https://learn.deeplearning.ai/courses/chatgpt-prompt-eng)


[^1]: clear != short

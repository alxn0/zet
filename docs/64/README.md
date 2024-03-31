# Sentence Window Retrieval

## What is it
Fetch a context from a document database based on the query, but then use a "larger context", namely the surrouding information or the window when feeding the LLM.

**Graphical exemple**
![29c9dc0af2e7536b49aeffa65c6feae0.png](29c9dc0af2e7536b49aeffa65c6feae0.png)

## Application

- Each sentence is index
- Take k sentence around (the window)
- Send this extended context to the LLM with the question

## Parameters
- Number of surrounding sentences (Window size)


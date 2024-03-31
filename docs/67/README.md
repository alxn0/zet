# Retrieval-Augmented generation

## What is it
- Retrieve facts from an external database that is not in the training set
- Less expensive than fine-tuning
- Can also retrieve the source with metadata
- Mitigate risk of hallucinations
- Also called **Grounding LLMS**

## Basic/naive pipeline
![Screenshot from 2024-02-22 14-02-12.png](Screenshot%20from%202024-02-22%2014-02-12.png)

1. **Ingestion**: Embed documentation on which we want to retrieve information
2. **Retrieval**
	- *Semantic search*: Compute the similarity between embedded user question and embedded documentation
	- *Get context*: retrieve k document (sections, pages, etc.)
3. **Synthesis**
	-  *Prompt* Add these document to the question, and modify the prompt accodingly
	-  *LLM response* Query LLM answer with previous prompt

**Example of prompt**
```python
prompt = f"""Here is the context: {context}
             Using the relevant information from the context,
             provide an answer to the query: {query}."
             If the context doesn't provide \
             any relevant information, \
             answer with \
             [I couldn't find a good match in the \
             document database for your query]
             """
```

## Limitation of basic RAG

1. **Inaccurate retrieval and limited contex**:  May capture irrelevant information or not capture the full context (see [sentence-window retrieval](../64) and [auto-merging retrieval](../636363636363)

2. **Lack of information validation**: RAG does not have a built-in mechanism to validate the whole process. See [triad of metrics](../65)

## Resource

[Deeplearning.ai - Understanding and Applying Text Embeddings](https://learn.deeplearning.ai/google-cloud-vertex-ai/)
[Deeplearning.ai - Building and Evaluating Advanced RAG Applications](https://learn.deeplearning.ai/building-evaluating-advanced-rag)

## Tools

[LlamaIndex](https://www.llamaindex.ai/)
[TruLens](https://www.trulens.org/)


# RAG Triad of metrics

![Screenshot from 2024-02-22 14-39-42.png](Screenshot%20from%202024-02-22%2014-39-42.png)[^1]

## Evaluation of the RAG application - Evaluate and iterate

### Common evaluation framework
- Start with Basic RAG
- Evaluate with RAG Triad
	- Failure modes related to context size (often)
- Iterate by changing parameters
- Re-evaluate RAG Triad
	- Do we see improvements in Context Relevance?
	- When context relevance goes up,  we often found improvement in groundedness (when context is not relevant, the LLM often look for knowledge in its pretraining)
	- What about other metrics?
- Gain insight on how hyperparameters work best with different documentation (e.g., academic papers, invoices)

## Feedback functions
![Screenshot from 2024-02-23 09-38-21.png](Screenshot%20from%202024-02-23%2009-38-21.png)[^1]

> Ground truth evals are human expert, while human evals is more general users
> From the academic litterature, LLM evals seems comparable to human evals

[^1]: From [deeplearning.ai](https://learn.deeplearning.ai/courses/building-evaluating-advanced-rag)
